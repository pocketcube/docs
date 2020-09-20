# Estrutura

A estrutura é um elemento importante para qualquer produto, é a parte do satélite que dá sustentação para todos os componentes embarcados dentro dele, desde os Eletrônicos até o sistema de energia. Portanto o objetivo consiste na análise estrutural de um satélite para a realização de missões espaciais a nível educacional. Deve-se fazer um estudo da estrutura a fim de suportar as cargas às quais o satélite será submetido, o que faz dela um elemento crítico para o projeto. Ela deve garantir que nenhum componente sofra dano e também facilitar a construção e acoplamento dos demais sistemas. Serão realizadas simulações numéricas baseadas no método de elementos finitos visando assegurar a integridade da estrutura.

# 1.1 Estrutura do Satélite

O projeto estrutural do satélite deve comportar todos os seus subsistemas visando diminuir a complexidade da montagem e união dos mesmos, além de garantir que nenhuma parte do satélite sofra danos, como por exemplo rachaduras, trincas no decorrer da missão. No contexto contemporâneo do New Space, ocorreu uma padronização de satélites, eles estão menores e com eletrônica mais potente comparado aos satélites tradicionais dos anos 1980. Dessa forma, para satélites educacionais, é recomendado algo que siga esse movimento do mercado Global, e que não possua sistemas tão complexos iguais os modelos antigos. Portanto, será analisado três tipos de satélite:

 - Nanosatelite, 1-10 kilograms;
 - Picosatelite, 0.01-1 kilograms;
 - Femtosatelite, 0.001-0.01 kilograms
 
 ###1.1.1 Nanosatélite
       - Modelo consolidade por universidades e pelo mercado;
       - Padronização em formato de cubo de 10cm x 10cm x 10 cm, o que caracteriza uma Unidade;
       - Formato mais usado: 3U (30cm x 10 cm x 10 cm);
       - Peso Padrão: de 3-5kg;
       
###1.1.2 Picosatélite 
      - Não convencional;
      - Mais utilizado para modelos educacionais; 
      - Formatos diferenciados, em forma de cilindro e cubo de aresta de 5cm x 5cm x 5cm;
      - Formato de cubo se chama PocketQube, e as medidas citadas se caracterizão por 1P;
      - Formato cilíndrico se chama Cansat, por ser pareciso com uma lata de refrigerante;
      - Peso Padrão de 500g à 1 kg;
      
###1.1.3 Fentosatelite
      - padronização de tamanho de cubo de 3cm x 3cm x 3cm;
      - Peso padrão de 100g;
      - Satélite pequeno e mais frágil em relação a sua estrutura;


## 1.2 Requisitos

Para obter êxito no projeto estrutural serão seguidos requisitos mecânicos na realização do dimensionamento da estrutura pois, há uma classificação, em relação a massa e dimensão, dos diversos tipos de satélite o que acarreta em diferentes formas de construção. Dessa forma serão adotados os seguintes requisitos para o projeto:
      - O satélite deve estar envolto por um Pocket 
      - A estrutura deve comportar um mecanismo para acoplamento 
      - A estrutura deve oferecer suporte para o sistema de alimentação de energia e para os dispositivos eletrônicos.
      - A estrutura deve ser capaz de suportar impacto e proteger os eletrônicos
      
  
## 1.3. Objetivos Específicos

      - A estrutura deve ser capaz de suportar o içamento quando acoplada ao seu lançador;
      - A estrutura deve ser feita de forma a suportar as solicitações mecânicas, térmicas;
      - A estrutura deverá oferecer suporte para o sistema de alimentação de energia e para os componentes eletrônicos;
      - Escolha do material adequado para estrutura com custo benefício acessível;
      - A estrutura deve ser capaz de abrigar um mecanismo de acionamento para Recuperação do Satélite;
      
## 1.4. Materiais

Para aplicação no projeto foram selecionados alguns materiais um copolímero de acrilonitrila, estireno e acrilato de butila (ASA), ele é um plástico funcional bastante utilizado no setor automotivo, construção civil, o acrilonitrila butadieno estireno (ABS) que também é um copolímero, ele é bastante utilizado no interior de automóveis, carcaças de aparelhos de cozinha, brinquedos ligas de alumínio, por exemplo alumínio 7075-T6, alumínio 6061-T6, materiais muito utilizados na indústria aeronáutica, na área de performance e chapa de aço SAE 1020.
O copolímero ASA apresenta boas propriedades mecânicas similares as do copolímero ABS, além de ter uma boa resistência contra raios UV (é atmosférico) fazendo com que o mesmo tenha uma aplicação mais efetiva para o projeto. A tabela abaixo apresenta um comparativo entre ambos.

Tabela 1: 

```eval_rst
.. image:: assets/estrutura/Tabela 1 Estrutura.PNG
  :align: center
  :width: 400
  :alt: Alternative text

  ..
  ```
 As Ligas de Alumínio 7075-T6 e 6061-T6 são materiais que combinam alta resistência mecânica aliada a leveza, ou seja, ambas apresentam ótimas propriedades mecânicas resultando em peças, estruturas capazes de suportar situações em que há uma aplicação de carga muito alta sobre a mesma. A tabela abaixo mostra um comparativo entre as ligas.
 
 ```eval_rst
.. image:: assets/estrutura/Tabela 2 Estrutura.PNG
  :align: center
  :width: 400
  :alt: Alternative text

  ..
```
O aço SAE 1020 geralmente aplicado em peças que vão sofrer esforço mecânico, é caracterizado pela combinação de força e alta ductilidade, que é a habilidade do material em ser dobrado ou moldado.

```eval_rst
.. image:: assets/estrutura/Tabela 3 Estrutura.PNG
  :align: center
  :width: 400
  :alt: Alternative text

  ..
```

## 2. Estação de Solo ou Ground Station 

Estação de Solo ou Ground Station é um centro de controle de dados de um satélite, em missões reais, estações de solos são organizadas por diferentes antenas, computadores e sistemas de telemetria e comunicação. Para missões a nível educacional, na qual esses satélites serão a nível atmosférico e sem um sistema de comunicação avançado e complexo como o tradicional, em um sistema atmosférico é necessário um sistema de recepcção de Dados e de computadores que estarão recebendo o dado do pequeno satélite após o seu lançamento. 

###Estrutura

A estrutura da Estação de solo educacional deverá seguir os seguintes Requisitos:
      - Suportar Choques Mecânicos e Impactos;
      - Alocar e Proteger componentes Eletrônicos;
      
### Materiais

Em falta


## 3. Sistemas de Lançamento

Um Satélite só realiza sua missão através de lançamentos espaciais, que colocam o seus satélites na órbita desejada. A nível educacional e não universitário, só iremos simular um lançamento, podendo realizar a medicção de dados atmosféricos. Em competições no mundo inteiro, os padrões para lançamentos atmosféricos são:

      - **Drone**: O lançamento do satélite pode ser feito via um drone modificado, com uma estrutura para carregar o satélitee depois soltá-lo em queda livre. O grande benefício se dá devido ao fato que pode ter o controle de quando lançar, e altura certa, já que o drone possui o sensor de altímetro. A problemática de se lançar com drone é que a legislação brasileira só permite uma altura máxima de 100 metros, o que pode atrapalhar o desenvolvimento de análise de satélite já que é uma altura considerada baixa para fazer medições a níveis mais profissionais. 
      
      - **Foguete experimental**: O foguete experimental é uma das formas mais usadas para lançamento de satélites educacionais, possui o objetivo de lançar o satélite e o mesmo ter que pousar em segurança com um paraquedas desenvolvido pela equipe. Vantagem: o meio que vai simular mais corretamente uma missão, pois simula um lançamento de um foguete. Desvantagens: Necessário contatar a força área, fechar o espaço áereo do local, sistema um pouco mais perigoso para realizar com alunos inexperientes já que o foguete pode cair em um raio que necessita ser calculado e envolve produtos inflamáveis e explosivos que são seus combustíveis.
      
      - ** Balão Atmosférico**: O balão atmosférico é um meio bem usado para fazer testes de satélites educacionais a níveis mais profissionais, alcançam uma altura de 18km a 37km. Ele sobe lentamente e cai em queda livre. Vantagem a altura que alcança, e possui resultados mais interessantes, na qual os alunos podem ver a curvatura da Terra através de uma Câmera e conseguem fazer experimentos mais profissionais. Desvantagens: o meio de desenvolvimento é mais caro por causa do gás hélio, e ficaria por volta de R$ 2500,00, mais o transporte da equipe para buscar o Balão que pode cair em um raio de 50km do seu ponto de lançamento, é necessário avisar o Força aérea devido ao fato de poder entrar em rota de colisão com um Avião.
