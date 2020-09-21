# Estação de Solo
Estação de Solo ou Ground Station é um centro de controle de dados de um satélite, em missões reais, estações de solos são organizadas por diferentes antenas, computadores e sistemas de telemetria e comunicação. Para missões a nível educacional, na qual esses satélites serão a nível atmosférico e sem um sistema de comunicação avançado e complexo como o tradicional, em um sistema atmosférico é necessário um sistema de recepcção de Dados e de computadores que estarão recebendo o dado do pequeno satélite após o seu lançamento. 

## Estrutura
A estrutura da Estação de solo educacional deverá seguir os seguintes Requisitos:  
- Suportar Choques Mecânicos e Impactos;
- Alocar e Proteger componentes Eletrônicos;

### Materiais

A estrutura da Ground Station pode ser construída utilizando-se materiais semelhantes aos aplicados na estrutura principal, ou seja, o copolímero ABS, o polímero ácido poliláctico (PLA), aço SAE 1020, além do alumínio 6061.

## Comunicação com o satélite

### Diagrama de Caso de Uso
  
***[inserir imagem aqui]***
  
Em nosso caso de uso, contaremos com 3 diferentes atores, cada um exercendo ações diferentes dentro do contexto do PocketQube. São eles:
- Satélite: coleta, armazena e envia dados;
- Servidor: trata e salva dados, além de enviar payload;
- Dashboard: apresenta dados.

## Tratamento dos dados do satélite

## Exposição de dados

### Diagrama NFR para Usabilidade
  
***[inserir imagem aqui]***
  
Para auxílio de definição de metas de requisitos não-funcionais do frontend, que será feito por meio de um aplicativo mobile, foi elaborado um diagrama inicial utilizando a abordagem do NFR Framework para ajudar na visualização de novos requisitos e na resolução de conflitos entre eles. Também será importante ao decorrer do projeto para conferir se os objetivos iniciais estão sendo atendidos.

Inicialmente foram levantados dois *soft goals*, de acordo com o Diagrama 1, que seriam uma **navegação facilitada** e **informações exibidas em um formato que possam ser interpretadas facilmente**. Para atingir o objetivo da simplificação de dados, será feito um esforço para pesquisar e entender quanto conhecimento o público-alvo possui na área, evitando que o uso de dados cause uma má experiência para o usuário. Para atingir o objetivo de navegação facilitada, serão usados: 
- Testes de usabilidade para validar as interações e o formato da dashboard no decorrer do projeto;
- Biblioteca SpriteKit para adicionar interatividade sem comprometer a usabilidade;
- Conhecimento dos desenvolvedores para evitar itens desnecessários.
