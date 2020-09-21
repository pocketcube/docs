# Estação de Solo
Estação de Solo ou Ground Station é um centro de controle de dados de um satélite, em missões reais, estações de solos são organizadas por diferentes antenas, computadores e sistemas de telemetria e comunicação. Para missões a nível educacional, na qual esses satélites serão a nível atmosférico e sem um sistema de comunicação avançado e complexo como o tradicional, em um sistema atmosférico é necessário um sistema de recepcção de Dados e de computadores que estarão recebendo o dado do pequeno satélite após o seu lançamento. O sistema da estação pode ser dividido em três grandes processos:
- Gateway;
- Tratamento de dados (Back-End);
- Disponibilização dos dados (Front-End).

O sistema de blocos representado abaixo mostra o funcionamento de uma estação de solo:

```eval_rst
.. image:: assets/relatorio_eletronica/diagrama_ground_station.png
  :align: center
  :width: 500
..

```

## Estrutura
A estrutura da Estação de solo educacional deverá seguir os seguintes Requisitos:  
- Suportar Choques Mecânicos e Impactos;
- Alocar e Proteger componentes Eletrônicos;

### Materiais

A estrutura da Ground Station pode ser construída utilizando-se materiais semelhantes aos aplicados na estrutura principal, ou seja, o copolímero ABS, o polímero ácido poliláctico (PLA), aço SAE 1020, além do alumínio 6061.

## Comunicação com o satélite

Os componentes eletrônicos relativos ao segmento de solo de um satélite educacional necessita de um sistema de comunicação entre o satélite e computador central, para receber dados e enviar comandos para o satélite. Portanto para os microcontroladores exigidos, será analisado os mesmos componentes da OBDH pois o sistema de TT&C em conexão com o OBDH:

```eval_rst
.. image:: assets/relatorio_eletronica/soil_table.png
  :align: center
  :width: 500
..

```

LoRa é uma tecnologia de radiofrequência que permite comunicação a longas distâncias (em áreas urbanas 3-4 Km de alcance, e em áreas rurais, até 12 Km ou mais), com consumo mínimo de energia. Suas principais aplicações são sistemas de IoT como sensores e monitores remotos, sobretudo aqueles operado a baterias, de mensagens curtas e em alguns casos em locais de difícil acesso.
LoRaWAN™ é o nome dado ao protocolo que define a arquitetura do sistema bem
como os parâmetros de comunicação usando a tecnologia LoRa.
O protocolo LoraWan™ implementa os detalhes de funcionamento, segurança, qualidade de serviço, ajustes de potência visando maximizar a duração da bateria 
dos módulos, e os tipos de aplicações tanto do lado do módulo quanto do servidor.

### Diagrama de Caso de Uso
  
```eval_rst
.. image:: assets/software/diagrama_caso_uso.png
  :align: center
  :width: 500
..

```
  
Em nosso caso de uso, contaremos com 3 diferentes atores, cada um exercendo ações diferentes dentro do contexto do PocketQube. São eles:
- Satélite: coleta, armazena e envia dados;
- Servidor: trata e salva dados, além de enviar payload;
- Dashboard: apresenta dados.

## Exposição de dados

### Diagrama NFR para Usabilidade
  
```eval_rst
.. image:: assets/software/diagrama_nfr_usabilidade.png
  :align: center
  :width: 500
..

```
  
Para auxílio de definição de metas de requisitos não-funcionais do frontend, que será feito por meio de um aplicativo mobile, foi elaborado um diagrama inicial utilizando a abordagem do NFR Framework para ajudar na visualização de novos requisitos e na resolução de conflitos entre eles. Também será importante ao decorrer do projeto para conferir se os objetivos iniciais estão sendo atendidos.

Inicialmente foram levantados dois *soft goals*, de acordo com o Diagrama 1, que seriam uma **navegação facilitada** e **informações exibidas em um formato que possam ser interpretadas facilmente**. Para atingir o objetivo da simplificação de dados, será feito um esforço para pesquisar e entender quanto conhecimento o público-alvo possui na área, evitando que o uso de dados cause uma má experiência para o usuário. Para atingir o objetivo de navegação facilitada, serão usados: 
- Testes de usabilidade para validar as interações e o formato da dashboard no decorrer do projeto;
- Biblioteca SpriteKit para adicionar interatividade sem comprometer a usabilidade;
- Conhecimento dos desenvolvedores para evitar itens desnecessários.
