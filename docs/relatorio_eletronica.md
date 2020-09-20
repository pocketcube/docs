# PocketQube

## On Board data Handling (OBDH)
// Determinação do placa controladora;  
// Integraçao com a EPS e o Payload  
// Comunicação com o TT&C  



## Telemetry, Traking and Command System (TT&C)
// Comunicar com a estação de solo;  
// Transmitir os dados do Payload para a estação de solo;  

## Payload
// Definir sensores e integrar com OBDH  
// Ter múltiplas missões  


Os payloads são o coração das missões no espaço. Sem os payloads, não haveria sentido em lançar um cubesat. Os payload para esses projetos são: 
- Observação da terra: Câmeras, sensores térmicos, radar, lasers, entre outros; 
- Clima espacial: Sondas Lugmir, magnetômetros, entre outros; 
- Meteorologia: Sensores de radiação eletromagnéticas;
- Comunicação: Antena e transmissores; 
- Científico: Medidores de plasma, varia de acordo com objetivo; 
- GPS: Antenas de Comunicação; 
- Exploração Espacial: Observação da galáxia e espaço profundo; 
- Outros: Utilizado para missões diversas até mesmo entretenimento;


### Camêra
O ESP32-CAM é uma versão especial da placa de desenvolvimento baseada no módulo ESP32S WiFi. É o modelo mais compacto da nova geração de placas com ESP32, contendo um slot para acoplamento da câmera e um slot micro-SD para gravar dados de tamanho máximo de 4GB. Muito eficiente, possui o módulo ESP-WROOM-32 que além de conter o ESP32, conta com um cristal de 40MHz. Tem suporte para as interfaces UART, SPI, I2C e PWM. Contém pinos para alimentação e programação, além de 16 portas GPIO, Conversor Analógico/Digital e botão reset ainda mais um LED maior para servir de flash. Abriga uma antena embutida e ainda, um encaixe para antena externa, com propósito de aumentar o alcance. Outro diferencial exclusivo do ESP32 CAM é que além de possuir conexão WiFi nativa, conta também com Bluetooth V4.2 embutido e microprocessador dual core 32-bit LX, de forma a tornar o projeto ainda mais prático e aumentar as possibilidades de uso. Tudo isso em um tamanho de 40.5 x 27 x 4.5 mm e 10 g. Na Figura X é mostrada uma foto do módulo.

```eval_rst
.. figure:: assets/relatorio_eletronica/ESP32-CAM.png
  :align: center
  :width: 400
  :alt: Alternative text

  ..

  Fig 1: Foto do módulo ESP32-CAM com a câmera OV2640

```

A ESP32-CAM suporta as câmeras OV2640 e OV7670. É possível ver na Tabela Y que o modelo OV2640 possui uma melhor resolução máxima, mas também é possível fazer um downgrade da qualidade se a taxa de transmissão estiver alta demais junto com outros sensores. O pixel deste modelo também é menor o que resulta em melhor qualidade na imagem. Toda essa captação de imagem tem um custo energético, mais que o dobro do consumo de potência em relação ao OV7670. A câmera escolhida para o projeto foi a OV2640 pela qualidade da imagem e pela flexibilidade, permitindo inclusive um downgrade de resolução se a taxa de transmissão for alta em determinado cenário. O valor do conjunto módulo+câmera foi de R$ 49,90.





# Estação de Solo

## Comunicação com o Satélite
// Dar comando para missões do PocketQube;
// Receber os dados do PocketQube







===================
## Satélite

Os componentes eletrônicos são essenciais para a validação do projeto, visto que, ao se lançar o PocketQube no espaço (ou na atmosfera) há a necessidade de aferir diversos dados para a sua manutenção. Além disso o satélite terá a missão de recolher algumas informações atmosféricas e de relevo.

O subgrupo de eletrônica tem por objetivo fazer medições da aceleração e velocidade angular, temperatura, pressão e umidade. Também verificar a localização geográfica do satélite em tempo real os quais serão todos obtidos através de sensoriamento eletrônico. A equipe vai utilizar microcontrolador para assimilar as medições feitas pelos sensores e para a comunicação entre o satélite e a estação solo.


### Microcontrolador

Para a escolha do microcontrolador foram considerados os modelos: Arduino UNO, ESP32 e Raspberry 0. Uma característica que é essencial para o projeto é o tamanho que a placa vai ocupar no satélite. A ESP32 possui dimensões 52mm x 25mm x 6mm sendo a menor placa entre as opções estudadas, e pesando 12,5 g, a mais leve.  

Como é possível ver na tabela, a placa da Espressif possui especificações técnicas mais robustas mesmo com menor área além do menor preço. Possui tanto conversor AD quanto DA o que ajuda a reconhecer medidas de diversos tipos de sensores. Outro motivo é a possibilidade de utilizar as bibliotecas do Arduino já que possui suporte no Arduino IDE além de ter conexão bluetooth e wifi. Isso ajudará os alunos a conhecerem soluções complexas feitas com ferramentas relativamente simples.

Segue o comparativo de microcontroladores que são utilizados normalmente em projetos:  

```eval_rst
=========================================== =========================================== =============================================================== ================================================================
Descrição                                   Arduino UNO                                 ESP32                                                           Raspberry Pi 0 
=========================================== =========================================== =============================================================== ================================================================
Alimentação                                 5V                                          2,2V ~ 3,3V DC                                                  5V/1.2A  
Bluetooth                                   Não Possui                                  Bluetooth Low Energy v4.2 (BLE)                                 Bluetooth Low Energy (BLE) 4.1 
Conversores ADC (Analógico para Digital)    6 ADC com 10-bit de resolução (1024 bits)   18 ADC com 12-bit de resolução (4096 its)                       16 ADS com 10 bit de resolução(1024 bits) 
Conversores DAC (Digital para Analógico)    Nenhum                                      2 DAC com 8-bit de resolução (256 bits)                         2 DAC com 8-bit de resolução (256 its) 
Corrente de Consumo                         Media de 15mA                               Media de 80mA                                                   Media de 150mA 
Entrada Regulada (VIN)                      Entre 7 e 12V                               Entre 5 e 9V                                                    Entre 3,3 e 5V 
Frequência de Operação:                     0 ~ 16 MHz                                  80MHz ~ 240MHz                                                  120 MHz 
Interfaces de Módulos                       I2C, SPI, UART e LED PWM                    SPI, SDIO, LED PWM, Motor PWM, I2S e IR                         mini HDMI (1080p60),Porta USB OTG On-The-Go) micro-usb 
Memoria FLASH                               32KB                                        4MB                                                             4MB 
Memoria RAM/SRAM                            2KB                                         520KB                                                           512KB 
Memória ROM/EEPROM                          4KB                                         448KB                                                           440KB 
Pinos de I/O                                23 pinos com 6 PWM                          34 pinos com 16 PWM                                             GPIO de 40 pinos 
Preço Médio (Modelo Original)               U$22,00 (Exterior) ou R$69,99 (Brasil)      U$14,95 (Exterior) ou R$38,90 (Brasil)                          U$38,90 Exterior) ou R$154,90 (Brasil) 
Processador                                 AVR® 8-bit RISC                             Xtensa® Dual-Core 32-bit LX6                                    Processador Broadcom BCM2835 ARM11 de 1GHz Single-core 
Sensores Embutidos                          temperatura e Toque Capacitivo.             temperatura (algumas versões), efeito Hall e Toque Capacitivo   temperatura algumas versões), efeito Hall e Toque Capacitivo 
Temperatura de Operação                     Entre-40°C e +85°C                          Entre -40°C  e+85°C                                             Entre-40°C e +85°C
Temporizadores                              3 Timers, um de 16-bit e dois de 8bit       4 Timers de 64-bit                                              4 Timers de 64-bit
Watchdog                                    1 Watchdog                                  4 Watchdogs                                                     1 Watchdog
WiFi                                        Somente com Shield                          2,4 GHz, 802.11 b/g/n/e/i (802.11n até 150 Mbps)                802.11 b/g/n
Dimensões(mm)                               68 x 53 x 12                                52 x 25 x 6                                                     65 x 30 x 5
=========================================== =========================================== =============================================================== ================================================================
```

Da fabricante chinesa Espressif Systems, a ESP32 é a solução mais integrada para aplicativos de Wi-Fi + Bluetooth da indústria com menos de 10 componentes. A ESP32 integra o interruptor da antena, RF balun, amplificador de potência, amplificador de recepção de baixo ruído, filtros, e módulos de gerenciamento de energia. Como tal, toda a solução ocupa uma área mínima de placa de circuito impresso (PCB). ESP32 é projetado para aplicativos móveis e Internet das Coisas (IoT). Tem muitos recursos dos chips de baixo consumo de última geração, incluindo controle de clock de alta resolução, modos de energia e escalonamento de energia dinâmico. Apresenta um coprocessador de ultra-baixo consumo (ULP Coprocessor), que permite delegar algumas tarefas (simples) para execução enquanto os processadores principais estão desligados. Ele possui suporte a SPI, UART e I2C (protocolos relativamente comuns), como também suporte a Infravermelho (IR) e SDIO (para interface com cartão de memória), e começa a se diferenciar, tendo CAN, Ethernet, DAC, Sensor de Toque, e I2S, que é uma interface de comunicação útil para comunicar com dispositivos de áudio.  

Dada suas características a ESP32 será o modelo a ser utilizado. Serão utilizados dois microcontroladores ESP32 no projeto, um no satélite para receber os dados dos sensores, reuní-los e enviar para um segundo microcontrolador em uma estação solo. Este irá receber os dados e enviá-los para o servidor local. A comunicação entre o satélite e a estação solo escolhida foi a comunicação LoRa por ser bastante flexível quanto ao local: Tanto em áreas urbanas quanto rurais, atendendo escolas nas cidades ou no campo. A LoRa também se caracteriza pela redução na complexidade do hardware, além de ter baixo consumo de energia. O microcontrolador escolhido tem módulo integrado com suporte para a LoRa.  


```eval_rst
.. figure:: assets/relatorio_eletronica/esp32-esquema.png
  :align: center
  :width: 400
  :alt: Alternative text

  ..

  Fig 1: Esquemático da ESP32

```

### Sensores

#### Atmosférico

O BME280 é um sensor digital combinado de umidade, pressão e temperatura com base em princípios de detecção comprovados. O módulo do sensor está alojado em um pacote LGA com tampa de metal extremamente compacto. O módulo dispõe de superfície de 12 x 15 mm e uma altura de 2,3 mm e ainda 1,4 g. Suas pequenas dimensões e seu baixo consumo de energia permitem a implementação em dispositivos movidos a bateria, como aparelhos, módulos GPS ou relógios. O BME280 atinge alto desempenho em aplicações que requerem medição de umidade e pressão. Essas aplicações emergentes de controle de automação residencial, navegação interna, condicionamento físico e refinamento do GPS exigem alta precisão. O sensor de umidade fornece um tempo de resposta altamente rápido para aplicações rápidas de reconhecimento de contexto e alta precisão geral em uma ampla faixa de temperatura.  

O sensor de pressão é um sensor de pressão barométrica absoluta com precisão e resolução extremamente altas e ruído drasticamente menor do que o Bosch Sensortec BMP180. O sensor de temperatura integrado foi otimizado para o menor ruído e a maior resolução. Sua saída é usada para compensação de temperatura dos sensores de pressão e umidade e também pode ser usada para estimativa da temperatura ambiente. O sensor fornece interfaces SPI e I²C e pode ser fornecido usando 1,71 a 3,6 V para a entrada  de alimentação do sensor e 1,2 a 3,6 V para a saída e alimentação da interface. As medições podem ser acionadas pelo host ou realizadas em intervalos regulares. Quando o sensor é desabilitado, o consumo de corrente cai para 0,1 µA.   

O BME280 é importante para o projeto primeiramente por ter dimensões pequenas, usar pouca carga de energia para ser acionado e calcular temperatura, pressão e umidade. É bastante preciso para o que é necessário para o projeto. A figura X ilustra o módulo e sua forma de ligação Sensor BME280 é bem simples, contando com somente com 4 fios, sendo 2 para alimentação que são os pinos VCC e GND e 2 para comunicação I2C, o SCL e SDA.  



```eval_rst
.. figure:: assets/relatorio_eletronica/BME280.png
  :align: center
  :width: 400
  :alt: Alternative text

  ..

  Fig 1: Módulo sensor BME 280

```

#### Acelerômetro e Giroscópio

Os dispositivos MPU fornecem a primeira solução de processador de movimento de 6 eixos integrada do mundo que elimina o giroscópio e acelerômetro associado a soluções discretas. Os dispositivos combinam um giroscópio de 3 eixos e um acelerômetro de 3 eixos no mesmo molde de silício junto com um Digital Motion Processor™ (DMP™) integrado capaz de processar algoritmos de fusão de sensores de 9 eixos complexos usando o MotionFusion™. Isto significa que é possível acessar magnetômetros externos ou outros sensores por meio de um barramento I2C mestre auxiliar, permitindo que os dispositivos reúnam um conjunto completo de dados do sensor sem intervenção do processador do sistema. Para rastreamento preciso de movimentos rápidos e lentos, o MPU6050 apresenta um giroscópio 	programável com escala de ±250, 500, 1000, 2000°/s e um acelerômetro de ±2, ±4, ±8, ±16g e tensão de Operação de  3 a  5V.

Foi estudado mais três tipos de sensores semelhantes ao MPU 6050: Itg3200 + Adxl345, o GY-BMI160 e o Mpu 9250 que é da mesma marca do módulo escolhido. O primeiro é o menor dos três, medindo 22x17x1 mm, e seu custo foi de R$ 98,99. O concorrente companheiro do marca foi o mais barato dos três custando R$ 58,50, porém, possui maiores dimensões tornando menos menos viável sua utilização para o projeto. O MPU6050 foi escolhido por suas dimensões (20x16x1mm) e peso (2,6 g), por seu valor econômico (R$ 17,00) e facilidade de implementação..A figura abaixo mostra o diagrama de blocos e em seguida o próprio MPU 6050.


```eval_rst
.. figure:: assets/relatorio_eletronica/MPU6050-1.png
  :align: center
  :width: 400
  :alt: Alternative text

  ..

  Fig 1: Diagrama de blocos MPU6050

```


```eval_rst
.. figure:: assets/relatorio_eletronica/MPU6050-2.png
  :align: center
  :width: 400
  :alt: Alternative text

  ..

  Fig 1: MPU6050

```

#### GPS

A série de módulos NEO-6 é uma família de receptores GPS autônomos apresentando o u-blox 6 de alto desempenho motor de posicionamento. Esses receptores flexíveis e econômicos oferecem inúmeras opções de conectividade em uma miniatura. Embalagem de 16 x 12,2 x 2,4 mm e 9 g. Sua arquitetura compacta e opções de alimentação e memória tornam os módulos NEO-6 ideal para dispositivos móveis operados por bateria com custos e restrições de espaço muito restritos. O GPS NEO-6M suporta diferentes modos de energia. Esses modos representam estratégias de como controlar os mecanismos de aquisição e rastreamento a fim de obter o melhor desempenho possível ou bom desempenho com consumo de energia reduzido. Durante uma inicialização a frio, um receptor no modo de desempenho máximo implanta continuamente o mecanismo de aquisição para pesquisar todos os satélites. Assim que o receptor tiver uma posição fixa (ou se houver informações de pré-posicionamento disponíveis), o mecanismo de aquisição continua a ser usado para pesquisar todos os satélites visíveis que não estão sendo rastreados. Depois que uma posição pode ser calculada e um número suficiente de satélites está sendo rastreado, o mecanismo de aquisição é desligado, resultando em uma economia significativa de energia. O mecanismo de rastreamento localiza continuamente os satélites adquiridos e outros satélites disponíveis ou emergentes. Um fator interessante é que mesmo que o mecanismo de aquisição seja desligado, os satélites continuam a ser adquiridos. 

No estudo feito para a escolha do módulo GPS do projeto foram considerados dois modelos: GY-GPSV3-NEO M8N e o GPS NEO-6M. Por suas especificações, os dois demonstram desempenho semelhantes, porém o primeiro dispõe de superfície de 36 x 25 mm contra 16 x 12,2 do segundo. Foi escolhido esse GPS por possuir um baixo consumo de energia e além de ser pequeno o que se faz ideal para satélites e, consequentemente para o projeto.



```eval_rst
.. figure:: assets/relatorio_eletronica/NEO-6M.png
  :align: center
  :width: 400
  :alt: Alternative text

  ..

  Fig 1: MPU6050

```