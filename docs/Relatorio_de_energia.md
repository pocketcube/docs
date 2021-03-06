# Eletric Power System 

O subsistema de suprimento energético - Electrical Power System (EPS) - é de grande importância, se não vital, para o desenvolvimento de qualquer projeto de satélite, sendo ele 
o responsável por garantir a geração, armazenamento, regulação e controle de energia e distribuição de energia para todos os outros subsistemas integrados.  Sullivan et. al (1989) 
o sistema de suprimento de energia corresponde a aproximadamente 20% da massa total do sistema de um satélite.  

Os nanosatélites operam com demandas reduzidas de energia dadas as suas restrições de massa e área, limitando as fontes energéticas e volume de baterias (Mahdi & Jaafer, 2014).  
Isso faz com que o EPS de qualquer projeto desse porte deva ser eficiente e flexível, ou seja, é necessário que o design do subsistema de energia atenda a todos os requisitos de  
potência do projeto e, ao mesmo tempo, possa ser reutilizado em outras missões, sem que este tenha que ser remodelado (HOLLWEG, 2016).  

A partir dos painéis solares, a energia elétrica é entregue ao módulo de potência e lá é condicionada, transferida e distribuída aos outros usuários do nanosatélites de acordo  
com suas necessidades de consumo (figura 1). O banco de baterias é necessário para que haja o armazenamento desta energia. É preciso compreender, também, que os sistemas de um  
satélite podem não funcionar o tempo todo ou ao mesmo tempo, então é preciso que a energia entregue seja gerenciada a fim de otimizá-la e garantir a vida útil do equipamento  
(Céspedes & Escobar, 2018).  


```eval_rst
.. image:: assets/Energia/DIAGRAMA 1 energia.png
  :align: center
  :width: 400
  :alt: Alternative text

  ..

  Figura 1.Configuração básica do Módulo de Potência. Fonte: Adaptado Céspedes & Escobar (2018).

```


## 1.1 Visão geral do suprimento de energia

Ferriani et al. (2006) considera que o sistema de potência dos satélites deve exercer várias funcionalidades, dentre elas ser capaz de produzir energia suficiente e eficiente,  
além de confiável. Por isso, os seguintes requisitos deverão ser atendidos para o projeto em questão na área de Power Supply:

  *Produzir energia através de células fotovoltaicas, suficiente para que o satélite funcione adequadamente;
  *Armazenar energia elétrica em baterias para que o satélite continue funcionando durante a noite ou em penumbras (sombras);
  *Ter proteções elétricas para o sistema de distribuição e condicionamento de potência;
  *Possuir sistemas de controle, regulação de fluxo de energia e condicionamento de temperatura.

A definição dos principais requisitos de EPS do PocketQube para Educação Básica foi feita adaptado de Wertz & Larson (1999). 

```eval_rst
.. image:: assets/Energia/Diagrama 2 Energia.png
  :align: center
  :width: 400
  :alt: Alternative text

  ..

  Figura 2. Arquitetura do EPS. Fonte: Adaptado de Wertz & Larson (1999).

## 1.2 Fonte de Energia

Dentre os elementos que compõe um EPS, a fonte de energia consiste em um componente gerador, e se mostra primeiramente como um ponto de partida para alimentação do sistema.  
O seu uso em satélites se dá, principalmente, em missões com maior previsão de duração ou em casos onde um suprimento de energia dependente exclusivamente de baterias resultaria  
em aumento expressivo no peso final do projeto. 

Os principais requisitos para esse componente consistem, essencialmente, em suas capacidades de gerar energia em diversos ciclos orbitais, suportar cargas elétricas e recarregar 
as baterias (Wertz & Larson, 1999).

Nesse tópico, são levantados os principais tipos de componentes geradores e posteriormente, a partir de uma análise comparativa, se propõe a utilização daquele que mais se  
adequa ao escopo do projeto.

### 1.2.1 Principais Fontes de Energia utilizadas em Satélites

Em um estudo aprofundado, Wertz e Larson (1999), elencam as quatro principais fontes geradoras de energia utilizadas em satélites, sendo elas: Células Solares Fotovoltaicas,  
Fontes de Energia Estática, Fontes de Energia Dinâmicas e Células a Combustível. A seguir, são apresentadas suas principais características e aplicações em satélites.

#### 1.2.1.1 Células Solares Fotovoltaicas

Essa fonte de energia baseia no efeito fotovoltaico para converter a radiação solar em energia elétrica para o sistema. É mais comumente aplicada em satélites em órbitas  
terrestres geossíncronas e, devido à sua confiabilidade, é a mais indicada para missões com potência menor que 15kW, consideradas baixa potência.

Entretanto, apesar de sua facilidade de aplicação, as células solares fotovoltaicas não são recomendadas para missões à planetas externos, devido a diminuição da radiação solar  
disponível, e nem para missões de mais longa duração, devido à degradação natural dos painéis.

Fatores inerentes a missões espaciais, tais como sombreamento, temperatura e vida da missão ou fatores genéricos como custos e riscos, são decisivos para a elaboração de um  
projeto solar para aplicação espacial.

#### 1.2.1.2 Fontes de Energia Estática

Esse tipo de componente gerador parte de uma fonte térmica (geralmente plutônio-238 ou Urânio-235) para conversão direta em energia elétrica, utilizando os conceitos termoelétrico  
e/ou termiônico. O tipo de fonte de energia estática mais utilizado em aplicações espaciais é o Par Termoelétrico, onde o gradiente de temperatura proveniente do decaimento  
lento da fonte radioativa é convertido em energia elétrica, com uma eficiência média de 5 a 8%.

Já a conversão a partir do conceito termiônico, possui uma eficiência de 10 a 20%, e se baseia na diferença de temperaturas entre dois eletrodos (emissor e coletor) mantidos  
vedados na presença de um gás ionizado. O eletrodo mais quente, emissor, emite elétrons através do espaço até o eletrodo mais frio, o coletor, onde eles se condensam e retornam  
ao emissor através da carga elétrica conectada externamente.

A aplicação desse tipo de fonte de energia implica em um sistema mais robusto e termicamente isolado, de forma a se conter as altas temperaturas necessárias para uma conversão  
eficiente.

####  1.2.1.3 Fontes de Energia Dinâmica

Assim como as fontes de energia estáticas, as fontes dinâmicas também utilizam uma fonte de calor para conversão em energia elétrica e necessitam de uma estrutura mais robusta.  
Entretanto, nesse caso, o sistema se baseia em um ciclo termodinâmico (Brayton, Stirling ou Rankine), utilizando um trocador de calor, para acionar um motor e realizar o processo  
de conversão.

Dentre as principais fontes de calor utilizadas por esse tipo de componente, tem-se radioisótopos, reação de fissão nuclear controlada e a energia solar concentrada. Nos casos  
de aplicação do último tipo, é utilizado sal eutético fundido para manter o calor latente e fornecer energia nos períodos de sombreamento, o que não é necessário nos outros  
tipos, uma vez que os mesmos fornecem calor de forma contínua.

Outro fator importante na implementação de um sistema de geração por fonte de energia dinâmica é a escolha do ciclo termodinâmico mais apropriado para o sistema, podendo ser  
empregados os ciclos de Stirling, Rankine ou Brayton, com eficiências de 15 a 35%.

#### 1.2.1.4 Células a Combustível

  Geralmente utilizadas em missões tripuladas, as células a combustível utilizam a energia dissipada em uma reação de oxidação para gerar eletricidade. Apesar dessa fonte utilizar  
  geradores independentes, esses necessitam de reposição de reagentes, sendo a relação de reposição diretamente proporcional à duração da missão.
  
  O tipo mais comum utilizado em aplicações espaciais é a célula baseada em Hidrogênio-Oxigênio, devido à sua potência específica alta, baixa massa de reagentes e subproduto útil 
  (água). A eficiência desse tipo de componente varia entre 50 a 80%, dependendo do consumo de alta ou baixa corrente.
  Dentre as principais vantagens desse tipo de componente gerador, destacam-se, além da sua eficiência, a sua confiabilidade, tempo de inicialização, desligamento instantâneo,  
  possibilidade de reversão da reação, e sua longa vida útil. Outro fator importante na sua utilização em missões tripuladas é a geração de água potável, que chega a 0,36 kg/kWh.
  
  Aliada a outros tipos de fontes geradoras, que possam suprir a demanda de energia durante o período de reversão (e, consequentemente, baixa carga elétrica), essa tecnologia  
  pode ser utilizada em quaisquer missões de longa duração.

###1.2.2 Fonte de energia escolhida no contexto do projeto

Baseando-se nos estudos de Patel (2005), Wertz & Larson (1999), Céspedes e Escobar (2018), De Paula & Magalhães (2019), Park, Chae e Oh (2019), Sanchez-Sanjuan et al. (2016) e  
Hollweg (2016), bem como, nas características e implicações de cada tipo de fonte de energia citada previamente e no contexto ao qual o projeto está submetido (destacando-se  
aqui o caráter educacional, a baixa demanda de potência, as aplicações em Low Earth Orbit e as limitações de peso e tamanho), entende-se que as células solares fotovoltaicas se  
apresentam como a opção mais adequada para alimentação do sistema. 

##1.3 Armazenamento de Energia

O sistema de armazenamento de energia pode ser feito com uso de baterias primárias e secundárias. As baterias primárias funcionam com a conversão de energia química em elétrica,  
mas não conseguindo fazer o processo reverso, ou seja, não podem ser recarregadas. Já as baterias secundárias convertem energia química em elétrica no momento da descarga, e  
energia elétrica em energia química durante a carga, podendo ser recarregáveis (De Paula & Magalhães, 2019, apud Wertz & Larson, 1999). Para um projeto de satélite educacional,  
as baterias utilizadas deverão ser secundárias, pois dependendo da órbita, nos momentos de sunlight, elas poderão ser recarregadas e serão utilizadas nas horas de eclipse  
(Ferriani et al., 2006).

A potência excedente gerada pelos painéis solares - única fonte de geração de energia viável em nanosatélites - em momentos de sunlight é armazenada nas baterias secundárias e  
utilizada pelos outros subsistemas do satélite em momentos de pico de consumo e/ou períodos de eclipse. A depender da órbita na qual o satélite irá trabalhar, a radiação solar  
pode ser zero, e por isso, a necessidade das baterias. Estes picos de consumo podem ser dados quando houver comunicação com a estação de solo.
 
De acordo com Patel (2005); Wertz & Larson (1999) apud De Paula & Magalhães (2019), Sanchez-Sanjuan et al. (2016) e Hollweg (2016), as baterias secundárias utilizadas em  
nanosatélites e que estão dominando o espaço são Níquel-Cádmio (NiCd), Níquel-Hidrogênio (NiH2), Níquel-metal-hidreto (NiMH), Lítio-íon (Li-Ion) e Lítio-polímero (Li-poly), 
sendo Li-Ion e Li-poly as mais utilizadas. O quadro 1 a seguir, adaptado de SAFT (2008), apresenta as baterias utilizadas no mercado e suas respectivas aplicações. Dentre elas,  
as baterias apropriadas para satélites são Li-Ion- cobalto e níquel - e as de NiH2 e NiCd.

      Tabela 1.  Baterias e suas respectivas aplicações no mercado.	
      
      ```eval_rst
.. image:: assets/Energia/Tabela Energia 1.png
  :align: center
  :width: 400
  :alt: Alternative text

  ..

```

Fonte: SAFT (2008).

Segundo o relatório The PocketQube Standard (2018), documento que orienta na construção de PocketQubes, materiais inflamáveis, tóxicos e potencialmente perigosos não devem ser  
utilizados, sendo um dos requisitos de segurança para as pessoas que manuseiam o equipamento. As baterias de Li-Ion e Li-poly seguem esta especificação. Além disso, outros  
critérios que devem ser avaliados antes de escolher a bateria para o nanosatélite são:
  *Dimensão das células individuais - flats ou circulares?
  *Longevidade - ciclo de vida máximo.
  *Saída de tensão.
  *Capacidade.
  *Massa.

###1.3.1	Baterias de NiCd e NiH2

As baterias de níquel-cádmio são baterias já utilizadas no mercado e, por isso, sua tecnologia já é bastante madura. Contudo, sua densidade energética acaba sendo  menor que as  
baterias mais recentes. Elas são utilizadas desde 1950 e seu uso está em declínio devido os problemas ambientais, sendo substituídas por baterias de NiMh e Li-Ion.

Um fator importante é que é necessário descarregá-las completamente, ou então elas irão criar o efeito memória, que são a formação de cristais nas placas das células.  
São baterias que preferem carga rápida e pulsada ao invés de cargas lentas e contínuas. A introdução de baterias com maior densidade energética e metais menos tóxicos está  
fazendo com que esta bateria perca espaço do mercado para modelos mais atuais, como já citadas as NiMh e Li-Ion. Para as baterias de NiCd:

  * Vantagens
      * Carga rápida e simples.
      * Muitos ciclos de carga e descarga, podendo chegar a 1000 ciclos.
      * A depender da condição de armazenamento, pode ter uma vida longa.
      * Desempenho bom em baixa temperatura e se sobrecarregada.
      * Menor preço se comparado aos das outras baterias.

  * Desvantagens
      * Baixa densidade energética (aprox. 40 Wh/kg).
      * Efeito memória.
      * Metais tóxicos - existem países limitando a sua produção, por exemplo.
      * Necessário sempre ser carregada, pois possui uma alta taxa de autodescarga.

  As baterias de níquel-hidrogênio (NiH2) começaram a ser vastamente utilizadas no armazenamento de energia aeroespacial a partir dos anos 90. A partir de 1993, começou a ser  
  utilizada em satélites de órbita geosíncrona (GEO) e sua primeira utilização pela NASA foi na missão do Telescópio Espacial Hubble de Órbita Terrestre Baixa (LEO), em 1990  
  (Dunlop, 1993). Algumas são as vantagens e desvantagens dessa bateria:
  
  * Vantagens
    * Bastante conhecida em aplicações aeroespaciais.
    * Não possui efeito memória.

  * Desvantagens
      * Baixa tensão de saída (1,2V)
      
### 1.3.2	Baterias de Li-Ion e Li-poly
	 
  As baterias de lítio-Ion e lítio-polímero podem ser consideradas iguais, porém com algumas sutis peculiaridades que as diferenciam. A diferença está no tipo de eletrólito 
  utilizado pelas baterias de lítio polímero.
	
  Desde a sua utilização nos anos 70, era utilizado eletrólito de polímero seco nas baterias de lítio-íon - película plástica- o que fazia com que a bateria devesse ser aquecida 
  a 60oC para que o fluxo de corrente ocorresse. Então, para que essa bateria fosse condutora a temperatura ambiente, um eletrólito gelificado foi adicionado e, embora a maioria  
  dessas baterias seja a base de cobalto, ela pode ser feita em diversos sistemas, como li-cobalto- NMC, li-fosfato, etc.
	
  No que concerne às diferenças entre as baterias de lítio-Ion e lítio-poly, as duas possuem cátodo e ânodo semelhantes e uma mesma quantidade de eletrólito. No entanto, as de 
  lítio polímero apresentam uma energia específica elevada e sua fabricação pode levar a uma bateria mais fina - cerca de 20% mais leves. Dessa forma, podemos elencar as principais 
  vantagens e desvantagens das baterias de lítio-polímero:
  
  * Vantagens
      * Menor espessura.
      * Flexibilidade em relação aos formatos, ou seja, não existe um padrão de fabricação.
      * 20% mais leve.
      * Mais segura e resistente à sobrecarga.
      * Não possui válvula de pressão - o aumento da pressão faz com que a célula comece a inchar, o que tende a não ocorrer caso a bateria seja utilizada e carregada de forma adequada.
      * Sem efeito de memória.
      * Maior intervalo de temperatura de operação que baterias de NiCd ou NiH2.

    * Desvantagens
      * Menor densidade energética e contagem de ciclos, quando comparada à bateria de Li-Ion (aprox. maior que 100 Wh/kg) - ainda sim, é três vezes melhor que NiCad e NiH2 (De Paula & Magalhães, 2019, apud Rocha, 2010).
      * Custo de produção - o fato do circuito de controle ser menor acaba por encarecer a produção.

  A seguir, é apresentado um quadro com os principais elementos a serem comparados entre estas baterias. 

          Quadro 2. Comparativo entre elementos principais das baterias estudadas.
          
 ```eval_rst
.. image:: assets/Energia/Tabela Energia 2.png
  :align: center
  :width: 400
  :alt: Alternative text

  ..
  
  Fonte: Adaptado de Oliveira (2018) apud Magalhães (2014); Jeppesen & Thomsen (2001); Trindade (2006).

## 1.4 Regulação e Controle de Energia
	A fase de regulação e controle de energia está intimamente condicionada ao componente gerador do sistema em questão. A técnica mais apropriada à um projeto depende da fonte  
  que o alimenta como, por exemplo, fontes de energia estática e dinâmica, que são reguladas por transferência direta (DET - Direct Energy Transfer). Já os projetos alimentados  
  por células fotovoltaicas são regulados por rastreamento de potência de pico (PPT – Power Point Tracking).
  
  Apesar de existirem mais de 500 topologias distintas para EPSs (Hong, 2011), essas duas classificações principais abrangem as topologias mais utilizadas, referindo-se à  
  configuração do sistema, no que diz respeito ao fornecimento de energia aos componentes, sendo que numa arquitetura DET a energia gerada é fornecida diretamente às cargas e o  
  excesso é dissipado. Já na arquitetura PPT, ou MPPT (Maximum Power Point Tracking), é utilizado um conversor CC-CC responsável por executar um algoritmo que determinará qual o  
  ponto de operação em tempo real.
  
  
 ```eval_rst
.. image:: assets/Energia/Diagrama 3 Energia.png.png
  :align: center
  :width: 400
  :alt: Alternative text

  ..
  
  Figura 3: Topologia de um sistema de potência. Fonte: Do autor (2020).
  
  Em ambos os tipos de arquitetura, vários métodos são utilizados para regulação do barramento principal. A seguir, serão listados os tipos de barramentos utilizados em EPS e 
  suas principais características, segundo De Paula & Magalhães (2019):
  
  ### 1.4.1 Barramento Não Regulado (BU)
 
 Visa simplificar o projeto do EPS, otimizando o sistema de energia centralizada e delegando às cargas a regulação da energia do barramento.

  ### 1.4.2 Barramento Regulado (BR)
 
 Aqui, ao contrário do anterior, o objetivo é a otimização do design dos componentes e simplificação da interface, e a regulação da energia do barramento é feita centralizadamente.
  
  ### 1.4.3 Barramento Semi-regulado (BS)
  
 Utiliza os dois métodos anteriores paralelamente, empregando dois barramentos principais, junto a um componente gerador independente, aumentando a oferta de energia.

  ### 1.4.4 Barramento Quase-regulado (BQ)
 
 Tem configuração semelhante ao Barramento Não Regulado, porém utiliza também um regulador de carga para a bateria (Battery Charger Regulator – BCR)

  ### 1.4.5 Barramento Híbrido (BH)

Utilizado em missões LEO para suprir as falhas existentes entre os barramentos regulados e não regulados.

A tabela a seguir apresenta as diferenças entre as configurações dos barramentos para os tipos de topologias DET e PPT.

 ```eval_rst
.. image:: assets/Energia/Tabela 3 Energia..png.png
  :align: center
  :width: 400
  :alt: Alternative text

  ..
  
      Figura 4: Diferentes técnicas de Regulação de Barramento aplicadas à topologias do tipo DET e PPT. Fonte: De Paula & Magalhães (2019).
      
 Dessa forma, considerando os diferentes modelos de regulação expostos, bem como a literatura de Jeppesen e Thomsen (2001), Eiterer (2017), Hollweg (2016), Wertz & Larson (1999), 
 De Paula & Magalhães (2019) e Mattos, Andrade, Schuch, Martins e Pinheiro (2017), entende-se que a topologia ideal para o Projeto PocketQube para educação básica seria do tipo PPT 
 (Power Point Tracking). Entretanto, a topologia específica, bem como a técnica de regulação de barramentos serão definidas posteriormente, de forma a se ter o dimensionamento dos  
 painéis solares como parâmetro. 
 
 ## 1.5 Distribuição de Energia

O sistema de distribuição da energia elétrica (Power Distribution Unit - PDU) consiste em cabos, barramentos de energia, componentes de proteção contra falhas e chaves (conversores)  
para ligar e desligar as cargas (dispositivos de segurança). Como subsistemas e cargas úteis trabalham com tensões diferenciadas, o barramento de distribuição pode precisar de regulagem  
para elevar ou diminuir a tensão, por meio de conversores DC-DC.

Os sistemas de distribuição de energia são centralizados ou descentralizados, dependendo da localização dos conversores. Na distribuição descentralizada os conversores estão  
alocados em cada carga separadamente, enquanto a abordagem centralizada regula a energia para todas as cargas de espaçonaves dentro do barramento principal. A distribuição  
descentralizada requer um barramento não regulado porque os conversores distribuídos regulam a potência. Uma vantagem do sistema centralizado é não ter a necessidade de projetar 
o EPS para diferentes aplicações (WERTZ & LARSON, 1999).

Em CubeSat, geralmente a rede de distribuição de energia para as cargas é feita de forma centralizada, sem o uso de conversores, devido às restrições de espaço.

## 1.6 Processo e design preliminar 

O processo e design preliminar consiste na seleção da metodologia a ser utilizada para dimensionamento dos elementos do EPS. Dessa forma, no presente tópico foram elencados as  
metodologias de dimensionamento de painéis, baterias e do controlador.

###1.6.1	Dimensionamento de painéis
Os painéis fotovoltaicos para satélites em órbita terrestre precisam ser projetados a fim de que atendam aos requisitos de carga dos outros subsistemas, principalmente nos períodos  
de sunlight e eclipse (Wertz & Larson, 1999). E para que eles sejam dimensionados, é preciso levar em consideração, como características das células, design de matriz solar, cálculos  
de dimensionamento, configurações, regulação e ambientes de radiação e térmicos.

Alguns problemas relacionados aos painéis solares devem ser levados em consideração no seu dimensionamento, como nível de potência demandado (pico e média), temperaturas de operação,  
sombreamento, ambiente de radiação, iluminação ou orientação, vida útil da missão, área do painel, massa e seu custo (Wertz & Larson, 1999). Por isso, a metodologia utilizada para o  
dimensionamento dos painéis do PocketQube para Educação Básica está no processo a seguir.

 ```eval_rst
.. image:: assets/Energia/Diagrama 4 Energia.png
  :align: center
  :width: 400
  :alt: Alternative text

  ..
  
  Figura 5. Metodologia para dimensionamento do painel solar. Fonte: Adaptado de De Magalhães & Paula (2019) apud Wertz & Larson (1999).
  
  #### 1.6.1.2	Potência produzida pelo painel solar
	A potência gerada pelo painel solar (Psa) é calculada a partir dos dados de potência necessária durante o sunlight (Pd) e eclipse (Pc) e pelos períodos de sunlight (Td) e  
  eclipse (Tc). A potência de painel solar é obtida pelas equações abaixo, respectivamente.
  
  ``eval_rst
.. image:: assets/Energia/Fórmulas 1 Energia.PNG.png
  :align: center
  :width: 400
  :alt: Alternative text

  ..


#### 1.6.1.3	Potência de saída por unidade de área do painel solar

A potência de saída é calculada pela multiplicação da eficiência da célula solar pela constante solar. Considerando a eficiência solar de 30,7%, a potência de saída para uma  
constante solar de 1367W/m², é calculada pela equação a seguir.

 ``eval_rst
.. image:: assets/Energia/Fórmulas 2 Energia.PNG.png
  :align: center
  :width: 400
  :alt: Alternative text

  ..

#### 1.6.1.4	Potência necessária BOL e EOL

	A potência de saída necessária para o começo de vida (Pbol) é calcula pela equação a seguir.

 ``eval_rst
.. image:: assets/Energia/Fórmulas 3Energia.PNG.png
  :align: center
  :width: 400
  :alt: Alternative text

  ..

A degradação por tempo de vida (Ld) é calculada como:

 ``eval_rst
.. image:: assets/Energia/Fórmulas 4 Energia.PNG.png
  :align: center
  :width: 400
  :alt: Alternative text

A potência de saída para o fim de vida é dada por:

 ``eval_rst
.. image:: assets/Energia/Fórmulas 5 Energia.PNG.png
  :align: center
  :width: 400
  :alt: Alternative text
  
  #### 1.6.1.5	Estimativa de área do painel solar

	O cálculo da área total de painel solar é a razão entre a potência do painel solar e a potência de saída do fim de vida. Desta maneira a área total é calculada pelas Equações (7) e (8).

 ``eval_rst
.. image:: assets/Energia/Fórmulas 6 Energia.PNG.png
  :align: center
  :width: 400
  :alt: Alternative text
  
 #### 1.6.1.6 Estimativa de massa do painel solar
	
  A massa estimada para o painel é obtida sabendo a potência gerada e a performance específica do painel, em W/Kg, dada pelo datasheet do equipamento escolhido.
  
   ``eval_rst
.. image:: assets/Energia/Fórmulas 7 Energia.PNG.png
  :align: center
  :width: 400
  :alt: Alternative text
  
  #### 1.6.1.7 Dimensionamento do painel solar

Esta etapa do dimensionamento visa determinar a quantidade de células em série (strings) e quantas strings em paralelo serão necessárias para compor o painel solar. Alguns dados 
terão de ser informados a partir do datasheet da célula solar selecionada, como potência, corrente e tensão da célula solar. A quantidade de células solares necessárias é dado por

``eval_rst
.. image:: assets/Energia/Fórmulas 8 Energia.PNG.png
  :align: center
  :width: 400
  :alt: Alternative text
  
 A quantidade de células em série é dado por,

``eval_rst
.. image:: assets/Energia/Fórmulas 9 Energia.PNG.png
  :align: center
  :width: 400
  :alt: Alternative text
  
  A quantidade de strings em paralelo é dado pela equação a seguir.
  
  ``eval_rst
.. image:: assets/Energia/Fórmulas 10 Energia.PNG.png
  :align: center
  :width: 400
  :alt: Alternative text
  
  ### 1.6.2	Dimensionamento do banco de baterias

O dimensionamento da bateria consiste na seleção da célula, da quantidade de células necessárias, no cálculo de capacidade de armazenamento e na estimativa de sua massa.

A partir da seleção de qual célula será utilizada no projeto, é possível determinar a quantidade de células necessárias a partir da tensão de barramento, de acordo com a equação 
a seguir (Wertz & Larson, 1999; Oraby et al., 2014).

   ``eval_rst
.. image:: assets/Energia/Fórmulas 11 Energia.PNG.png
  :align: center
  :width: 400
  :alt: Alternative text
  
  A tensão de barramento é, então, calculada por
  
    ``eval_rst
.. image:: assets/Energia/Fórmulas 12 Energia.PNG.png
  :align: center
  :width: 400
  :alt: Alternative text
  
  A depender da órbita que o PocketQube irá se posicionar, é necessário saber qual será a sua órbita em eclipse. Isso significa que a energia gerada pelos painéis solares deverão  
  ser direcionadas para o carregamento do banco de baterias para que o sistema continue funcionando nos períodos de eclipse. Então, essa energia consumida pelo PocketQube durante  
  esse período é calculada pela potência de consumo e o tempo de eclipse.


    ``eval_rst
.. image:: assets/Energia/Fórmulas 13 Energia.PNG.png
  :align: center
  :width: 400
  :alt: Alternative text
  
  A capacidade de armazenamento da bateria pode ser calculada considerando a profundidade de descarga da bateria (Deep of Discharge - DoD) - referente à quantidade  de carga  
  retirada da bateria num ciclo típico de funcionamento, expressa em percentagem da capacidade nominal desta -, número de células de bateria e eficiência de transmissão entre  
  a bateria e a carga.

    ``eval_rst
.. image:: assets/Energia/Fórmulas 14 Energia.PNG.png
  :align: center
  :width: 400
  :alt: Alternative text
  
  É possível obter a capacidade da bateria em Ah - Ampere-hora- pela equação a seguir.

    ``eval_rst
.. image:: assets/Energia/Fórmulas 15 Energia.PNG.png
  :align: center
  :width: 400
  :alt: Alternative text
  
  Agora, para dimensionar a massa das baterias, é necessário saber o valor de densidade de energia específica - em Wh/Kg - e a capacidade de armazenamento da bateria calculada anteriormente.

    ``eval_rst
.. image:: assets/Energia/Fórmulas 16 Energia.PNG.png
  :align: center
  :width: 400
  :alt: Alternative text
  
  ## 1.7	Consolidação do EPS no PocketQube para Educação Básica
	
  O PocketQube para Educação Básica tem como premissa fomentar e facilitar o aprendizado de alunos de educação básica nas áreas de exatas, bem como promover uma maior aproximação 
  com assuntos que parecem tão complexos no âmbito da educação fundamental e secundarista. Dessa forma, a conformação do satélite deverá permitir que o aluno consiga, de maneira  
  didática, montar o seu satélite e compreender a função e o significado de cada subsistema.
	
  Levando em consideração o subsistema de energia, o EPS, este deverá estar disposto de maneira que se possa montá-lo junto aos outros subsistemas. Ainda não foi possível definir  
  quais as dimensões e qual a melhor forma para que estes equipamentos sejam confeccionados e possam ser encaixados: se estarão em cases ou não. No entanto, este deverá ser o principal 
  requisito para os próximos pontos de controle.


BIBLIOGRAFIA

DE PAULAA, Elaine de Souza Ferreira; DE MAGALHÃES, Renato Oliveira. ANÁLISE DE BALANÇO DE POTÊNCIA, PROJETO PRELIMINAR DE PAINEL SOLAR E DIMENSIONAMENTO DE BATERIA DE UM CUBESAT 3U PARA DETECÇÃO DE RAIOS. 2019.

Sullivan, D.O. Satellite power system topologies. ESA Journal, v.13, p. 77 - 88, 1989.

Wertz, J. R., Larson W. J., 1999. “Space Mission Analysis and Design”. Microcosm, 976 pp; 3rd edition.p.407-427.
HOLLWEG, Guilherme Vieira. Arquitetura Distribuída de Sistema de Energia para CubeSat. 2016.
MAHDI, M. C.; JAAFER, J. S.; SHEHAB, A.-A.-R. Design and Implementation of an Effective Electrical Power System for Nano-Satellite.International Journal of Scientific & Engineering Research, [S.l.], v.Volume 5, n.Issue 5„ p.29–, May 2014.
SANCHEZ-SANJUAN, Sergio; GONZALEZ-LLORENTE, Jesus; HURTADO-VELASCO, Ronald. Comparison of the incident solar energy and battery storage in a 3U CubeSat satellite for different orientation scenarios. Journal of Aerospace Technology and Management, v. 8, n. 1, p. 91-102, 2016.
Patel, Mukund R. “Spacecraft Power Systems”. 1st ed. Boca Raton: CRC Press, 2005 658p.
The PocketQube Standard. Issue 1. 7 th of June, 2018. Page 2

CÉSPEDES, J. E. S.; ESCOBAR, R. F. Diseño e Implementacion de un Modulo de Gestion de Energia para un Pico-Satelite Tipo Cubesat. KnE Engineering, v. 3, n. 2, p. 913-930, 11 Feb. 2018.

Rocha. S. L., 2010. “Power Control Unit Development Model of the ITASAT University Satellite Energy Supply Subsystem”. Instituto Tecnológico de Aeronáutica, São José dos Campos.
Jeppesen,Thomas, Thomsen, Michael. 2001. Power supply for DTU’s Cubesat
SAFT. Rechargeable Li-ion Battery Systems: Light Energy Storage for Space Applications Catalogue. 2008.

DUNLOP, James D. NASA handbook for nickel-hydrogen batteries. National Aeronautics and Space Administration, Scientific and Technical Information Branch, 1993.


OLIVEIRA, Túlio Costa de. Estudo da tecnologia empregada em veículos elétricos com autonomia estendida: comparativo experimental com veiculos híbridos. 2018.

MAGALHÃES, B. F. de O. Hibridação de veículo automóvel. 2014. 158 p. Dissertação (Mestrado integrado em engenharia mecânica) — Universidade do Porto.
TRINDADE, Rafael Heleno Ladeira. Estudo das características de baterias recarregáveis possíveis de serem utilizadas no projeto Satélite Universitário, ITASAT. XII Encontro de Iniciação Cientí ca e Pós-Graduação do ITA XII ENCITA, 2006.
FERRIANI, Vinícius Meirelles Pereira et al. Estudo Do Subsistema De Suprimento De Energia Do Satélite Universitário ITASAT. ENCONTRO DE INICIAÇÃO CIENTÍFICA E PÓS-GRADUAÇÃO DO ITA–XII ENCIITA, 2006.
