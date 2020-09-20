# Apêndices

## Apêndice 1 - Decisôes de arquitetura de software

### Arquitetura cliente-servidor

No início, pela natureza do projeto, já era de conhecimento da equipe que a provável arquitetura seria cliente-servidor. Uma vez que seria necessário um software para visualizar os dados e outro para recebê-los dos microcontroladores. Porém, ainda não estava decidido como eles se comunicariam. Foram analisadas duas opções: REST e WebSockets.

* REST

Essa arquitetura possui algumas variações, dependendo do fluxo dos dados apresentados. Geralmente, nessa arquitetura, o cliente se comunica com o servidor via HTTP através de uma API na arquitetura REST (REpresentation State Transfer)[1]. Como o nome indica, com esse tipo de API, o servidor irá transferir a representação atual do recurso requisitado.

Porém, essa arquitetura não permite utilização de dados em tempo real: como o cliente recebe uma representação dos dados no momento da requisção, ele não é informado caso o estado daquele recurso seja modificado. 

Exemplo: dado momento de tempo T<sub>n</sub> de uma requisição HTTP feita para a API REST, o estado C<sub>n</sub> do recurso de temperatura é igual a 30 graus Celsius. No tempo T<sub>n+1</sub>, a temperatura C<sub>n+1</sub> é 30.5 graus Celsius. Essa mudança não será informada ao cliente enquanto ele não fizer a próxima requisição. 

* WebSockets

Então, dada a necessidade de ter as informações em tempo real, foi escolhida a tecnologia de WebSockets, segundo a Mozilla: "(...) WebSockets é uma tecnologia avançada que torna possível abrir uma sessão de comunicação interativa entre o navegador do usuário e um servidor. Com esta API, você pode enviar mensagens para um servidor e receber respostas orientadas a eventos sem ter que consultar o servidor para obter uma resposta." [2].

Essa tecnologia encaixou muito bem com a nossa proposta de coletar dados em tempo real e transmiti-los em tempo real sem onerar o servidor, portanto escolhemos ela.

### Arquitetura microserviços

* Monolito

A arquitetura de monolitos é uma forma de organizar todo o servidor em apenas um módulo. Nessa estratégia, o acoplamento entre os componentes do módulo aumenta conforme a complexidade da solução. Assim, há maior necessidade de recursos para todo o módulo, mesmo que alguns componentes sejam mais utilizados que outros.

Como o nosso projeto visa utilizar processamento de baixo custo, é necessário que se consuma a menor quantidade de recursos possível e que não haja capacidade de computação ociosa.

* Microserviços

A arquitetura de microsserviços permite um baixíssimo nível de acoplamento entre os componentes, uma vez que cada módulo opera independente de outro, ocorrendo a comunicação entre eles apenas se necessário. 

No contexto do PocketQube, o microcontrolador coleta e envia dados de vários sensores para o nosso servidor, podendo aumentar ou diminuir a frequência conforme a disponibilidade do sensor. 

Em certo momento, por exemplo, um sensor pode estar indisponível enquanto todos os outros estão operando e não é uma escolha interessante onerar a plataforma alocando recursos para um serviço que não está sendo utilizado.

Outra vantagem para esse contexto é que sempre que um novo sensor for adicionado, basta escrever um servidor que irá receber esses dados sem interferir nos outros que já foram criados.

Portanto, essas características guiaram nossa escolha pela abordagem de microsserviços.

### Uso do MQTT

Como a entrada de dados em um sistema com vários sensores é muito alta, mas nem sempre os servidores podem estar disponíveis para lidar com todos, viu-se necessária colocar uma interface de comunicação de gerenciamento entre a entrada de dados pelos microcontroladores e pelos microserviços.

A estratégia de fila, então, foi a escolha mais apropriada a fazer. Em ambientes IOT, o padrão de envio de mensagens em filas tanto no mercado quanto na academia é o de filas, inclusive já sendo utilizadas em plataformas oferecidas pela IBM [3] ou até mesmo em algumas implementações de CubeSats nas universidades [4].

Dentre as várias implementações de gerenciadores, o Message Queue Telemetry Transport (MQTT) [5] se define como o standart para mensageria em IOT e portanto escolhemos essa abordagem.

### Experiência do Usuário e decisão da tecnologia do cliente

* Aplicação mobile

Já faz certo tempo que o iPad foi inserido no contexto educacional ao redor do mundo. Neste contexto, muitas pesquisas foram realizadas tentando compreender o impacto da inserção dessa tecnologia nas escolas e universidades. A pesquisa "*The iPad in education: uses, benefits, and challenges.*", realizada no Canadá com mais de 6000 alunos apresentou 13 benefícios do uso dos iPads nas escolas. São eles: 

* aumento da motivação do alunos; 
* facilidade de acesso a informação; protabilidade do dispositivo; 
* facilidade para anotações e organizar tarefas; 
* qualidade da apresentação dos estudades; qualidade da apresentação dos professores; 
* aumento da colaboração entre estudantes e professores; 
* alunos podem trabalhar/aprender no seu próprio ritmo; 
* desenvolvimento de habilidade de TI por parte dos professores; e
* desenvolvimento de habilidade de TI por parte dos alunos [6].

Por estes motivos, foi optado pelo iPad como plataforma do nosso frontend. Lembrando que devido a nossa arquitetura de backend e microsserviços estas interações podem ser expansíveis para outras plataformas. Entretanto, estas ficam fora do escopo inicial do projeto.

* Testes de usabilidade 

Ao longo do projeto, serão realizado testes de usabilidade a partir de protótipos de baixa fidelidade. Segundo Jakob Nielsen, são necessários apenas 5 usuário necessário para identificar problemas na usabilidade de um produto [7]. Desta forma, para cada incremento do nossa aplicação será realizado testes de usabilidade. O relatório deles será apresentando no anexo de cada ponto de controle.

### Referências

[1] Architectural Styles and
the Design of Network-based Software Architectures. FIELDING, R. 2000. https://www.ics.uci.edu/~fielding/pubs/dissertation/top.htm. Acesso em 20/09/2020.

[2] WebSockets. MOZILLA. 2020. https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API. Acesso em 20/09/2020.

[3] Getting to know MQTT - Why MQTT is one of the best network protocols for the Internet of Things?. YUAN, M. IBM Developer. 2017. https://developer.ibm.com/articles/iot-mqtt-why-good-for-iot/. Acesso em 20/09/2020.

[4] OpenOrbiter: A Low-Cost, Educational Prototype CubeSat
Mission Architecture. STRAUB, J. et al. 2013.

[5] MQTT Homepage. MQTT. https://mqtt.org/. Acesso em 20/09/2020.

[6] The iPad in education: uses, benefits, and challenges - A survey of 6057. KARSENTI; THIERRI; FIEVEZ, A. Aurélien Fievez. 2013.

[7] The "magic number 5" is it enough for web testing?. NIGEL, B. et al.  CHI'03 extended abstracts on Human factors in computing systems. 2003.

## Apêndice 2 - Guia de acessos 

### Acesso ao repositório do backend (servidor & microsserviços)

Repositório com a aplicação backend e microsserviços, informações de como rodar, estão descritas no README.md da aplicação

[https://github.com/pocketcube/backend](https://github.com/pocketcube/backend)

### Acesso ao repositório do frontend ( Aplicação mobile)

Repositório com a aplicação mobile, informações de como rodar, estão descritas no README.md da aplicação

[https://github.com/pocketcube/app](https://github.com/pocketcube/app)

### Documentação do projeto 

Repositório com a documentação do projeto.

[pocketcube.readthedocs.io/](pocketcube.readthedocs.io/)