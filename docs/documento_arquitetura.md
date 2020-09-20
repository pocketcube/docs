# Documento de Arquitetura

Este anexo apresenta uma estrutura da arquitetura do projeto em nível de backend (servidor e banco de dados) e frontend (aplicativo mobile). Vale-se ressaltar que a comunicação entre cliente e servidor ocorre por **JSON (JavaScript Object Notation)**,  que é uma notação bastante utilizada em arquitetura de microsserviços por ser de fácil compreensão, e apresentar vários suportes na parte de parsear o objeto entre o cliente e servidor.
  
A comunicação acontecerá através de protocolos de comunicação HTTP e WebSockets, utilizando as arquitetura REST e MQTT.
  
```eval_rst
.. image:: assets/Software/diagrama_comunicacao.png
  :align: center

  ..

  Figura 1 - Diagrama de Comunicação.
```

A partir desse diagrama, desenvolvemos o diagrama de sequência abaixo, detalhando o fluxo de dados e interações entre cada um dos atores:
  
***<div align="center">[inserir imagem aqui]</div>***  
*<div align="center">Figura 2 - Diagrama de Sequência.</div>*
  

## Backend - Servidor e Banco de Dados
### Contexto

Dado o contexto de alto volume de entrada e saída de dados, e a possibilidade de aumentar sendo recebidos por diferentes sensores, e enviando em tempo real para o aplicativo, optamos pela solução de microsserviços.
  
Uma vez adicionado um novo sensor, é também adicionado um novo serviço que irá cuidar desse sensor, recebendo e transmitindo os dados recebidos, seja para outros serviços ou para algum cliente.
  
Como o nosso cluster de serviços (servidores) estará instalado em uma Raspberry Pi, optamos por uma linguagem leve e escalável, além de ter uma interoperabilidade de fácil configuração com a plataforma.
  
Especificamente sobre o serviço de streaming de vídeo, será necessário receber e tratar os dados do vídeo recebido pela câmera da ESP, então uma linguagem que ofereça bibliotecas robustas para essa tarefa foi um diferencial para a escola entre elas.
  
Por último, e não menos importante, dadas as necessidades, os riscos levantados e tempo para execução do projeto, escolhemos tecnologias que sejam fáceis de configurar, que o grupo possua alguma experiência prévia e que forneça um bom nível de produtividade no desenvolvimento.


### Tecnologias

Por estes motivos, o **Python** foi definido como linguagem para criação dos nosso microsserviços. Além do Python, serão necessárias algumas tecnologias para dar suporte à nossa arquitetura, como comunicação entre os serviços, API gateway, proxy reverso e configuração de deploy/ambiente.
  
Para a conteinerização e isolamento de ambiente de cada serviço, foi escolhido o **Docker**, pois ele é leve, possui boa interoperabilidade com a Raspberry Pi e possui uma configuração fácil e simples para atender a velocidade e o curto espaço de tempo que possuímos para desenvolver o projeto.
  
Para a comunicação entre os sensores e os serviços, iremos utilizar a estratégia de *message broker*, utilizando o **RabbitMQ**. Essa estratégia é necessária pois os serviços irão receber uma alta carga de entrada e saída de dados e, para evitar sobrecarga ou perda dos dados, optamos por colocá-los em uma fila (*first in first out*) para controlar o fluxo e enviar os dados assim que houver disponibilidade.


### Comunicação entre os sensores e o servidor

Os dados coletados pelos sensores serão enviados via LoraWAN para uma ESP32 receiver, na estação de solo, que estará conectada a nossa rede local e enviará os dados para o *message broker*. A partir daí, os microsserviços irão buscar os dados publicados na fila, e irão tratar e transmitirão para o frontend.


### Estrutura de Pacotes

Como os serviços de sensores, como os de temperatura ou umidade, funcionam de forma parecida, eles podem compartilhar da mesma estrutura de pacotes, descrita a seguir:
  
***<div align="center">[inserir imagem aqui]</div>***  
*<div align="center">Figura 3 - Estrutura de pacotes do servidor/microsserviços para os sensores.</div>*
  
O pacote *app/* é responsável por agrupar os pacotes *api/* e *queue/* que irão cuidar da recepção dos dados pelo sensor e comunicar com a fila de mensagens, respectivamente.
  
O pacote *queue/* é responsável por buscar os dados na fila e comunicar ao pacote *api/* que existe um novo dado para ser processado e enviado.
  
O pacote *api/* é responsável por todo o *pipeline* de tratamento, serialização, carga e envio dos dados para o frontend via WebSocket.


## Frontend - Aplicativo Mobile

De acordo com os requisitos levantados, observou-se que muitas escolas utilizam *iPads* no ambiente educacional. Esses tablets permitem que a experiência seja mais imersiva em relação a sites. Dessa forma, optou-se pelo desenvolvimento de uma aplicação mobile em iOS utilizando-se a linguagem **Swift**.


### Arquitetura

O diagrama de pacotes fornece uma compreensão das camadas na construção de um software e sua comunicação. Nesse projeto, foi proposta a *Clean Architecture*, postulada por Robert C. Martin (conhecido como Uncle Bob), na estrutura das telas. E, para a comunicação entre elas, foi proposto um *coordinator*.
  
A seguir, estão apresentados os pacotes da aplicação mobile e cada uma das suas camadas. A camada do *coordinator* tem como objetivo controlar a navegação dentro do app. A  *scene* é a estrutura de uma tela propriamente dita (suas responsabilidades serão melhor descritas na próxima subseção). A camada de rede, definida como *network*, é responsável por fazer *requests* HTTP ao servidor. Por fim, as *entities* representam os objetos do mundo real, no caso as informações relacionadas ao nosso satélite.
  
***<div align="center">[inserir imagem aqui]</div>***  
*<div align="center">Figura 4 - Diagrama de pacotes da aplicação mobile.</div>*


### View-Interactor-Presenter (VIP)

O VIP foi proposto a partir dos princípios da *Clean Architecture*. Ele é composto por cenas que consistem numa unidade reduzida de funcionalidade, como autenticação, configuração, visualização de perfil, entre outras. As cenas possuem módulos de formatação de dados e interação com o usuário. Protocolos conhecidos como *boundaries* fazem a comunicação entre os módulos.
  
Cada cena do VIP apresenta as seguintes camadas: View, Model, Interactor, Worker e Presente. Este fato auxilia na divisão de responsabilidades, manutenção e testabilidade. Dessa forma, as cenas representam conjuntos de classe:

***<div align="center">[inserir imagem aqui]</div>***  
*<div align="center">Figura 5 - Diagrama de classes de uma cena do VIP, na arquitetura mobile.</div>*
  
***<div align="center">[inserir imagem aqui]</div>***  
*<div align="center">Figura 6 - Pacote com estrutura do app.</div>*


### Tecnologias

No desenvolvimento da aplicação para iOS serão utilizadas as seguintes tecnologias:
- **Alamofire:** Framework utilizado para chamadas HTTP. É o mais forte na comunidade de iOS, com cerca de 21 mil estrelas no GitHub.
- **UIKit:** SDK nativa do iOS utilizada no desenvolvimento de componentes visuais.
- **SpriteKit:** Permite a visualização/interação em objetos 2D/3D no iOS. É um framework nativo bastante utilizado no desenvolvimento de jogos.
- **Danger:** Ferramenta de análise estática de código, funciona muito bem quando integrada à CI.
- **Github Actions:** Ferramenta de integração contínua para projetos Open Source, gratuita e nativa do GitHub.


## Referências
- MARTIN, Robert. Arquitetura Limpa: o Guia do Artesão Para Estrutura e Design de Software. 1ª Edição. Editora Alta Books, 2019.
