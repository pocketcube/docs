# Lançador

## Sistema de lançamento

Um Satélite só realiza sua missão através de lançamentos espaciais, que colocam o seus satélites na órbita desejada. A nível educacional e não universitário, só iremos simular um lançamento, podendo realizar a medicção de dados atmosféricos. Em competições no mundo inteiro, os padrões para lançamentos atmosféricos são:

- **Drone**: O lançamento do satélite pode ser feito via um drone modificado, com uma estrutura para carregar o satélitee depois soltá-lo em queda livre. O grande benefício se dá devido ao fato que pode ter o controle de quando lançar, e altura certa, já que o drone possui o sensor de altímetro. A problemática de se lançar com drone é que a legislação brasileira só permite uma altura máxima de 100 metros, o que pode atrapalhar o desenvolvimento de análise de satélite já que é uma altura considerada baixa para fazer medições a níveis mais profissionais. 

- **Foguete experimental**: O foguete experimental é uma das formas mais usadas para lançamento de satélites educacionais, possui o objetivo de lançar o satélite e o mesmo ter que pousar em segurança com um paraquedas desenvolvido pela equipe. Vantagem: o meio que vai simular mais corretamente uma missão, pois simula um lançamento de um foguete. Desvantagens: Necessário contatar a força área, fechar o espaço áereo do local, sistema um pouco mais perigoso para realizar com alunos inexperientes já que o foguete pode cair em um raio que necessita ser calculado e envolve produtos inflamáveis e explosivos que são seus combustíveis.

- **Balão Atmosférico**: O balão atmosférico é um meio bem usado para fazer testes de satélites educacionais a níveis mais profissionais, alcançam uma altura de 18km a 37km. Ele sobe lentamente e cai em queda livre. Vantagem a altura que alcança, e possui resultados mais interessantes, na qual os alunos podem ver a curvatura da Terra através de uma Câmera e conseguem fazer experimentos mais profissionais. Desvantagens: o meio de desenvolvimento é mais caro por causa do gás hélio, e ficaria por volta de R$ 2500,00, mais o transporte da equipe para buscar o Balão que pode cair em um raio de 50km do seu ponto de lançamento, é necessário avisar o Força aérea devido ao fato de poder entrar em rota de colisão com um Avião.

## Deployer
No processo de definição do deployer o sistema de lançamento é crucial para definir, pois o deployer tem duas interfaces importantes uma de conexão com lançador e outra de encaixe do satélite, entre os requisitos do deployer está justamente a facilidade e segurança de integração do satélite durante o tempo de missão dele, buscando garantir integração do satélite com o lançador visando uma segurança da payload e dos componentes embarcados e lançados. 

- **Drone Deployer**: pelo drone o sistema de deployer consiste em um encaixe, geralmente na barriga do drone, para que o satélite possa conseguir altitude no voo, a definição da estrutura do deployer impacta em duas decisões estruturais no satélite, a primeira é que definição de ter ou não um paraquedas agregado na estrutura do satélite, caso a missão necessite um tempo de queda livre, o deployer precisa soltar o satélite durante o seu voo, caso não necessite o drone pode retornar com satélite, fazendo o deployer ser semelhante a um sistema de garra. 

```eval_rst
.. image:: assets/estrutura/drone-deployer.jpg
  :align: center
  :width: 400
..
```

- **Foguete Deployer**: o sistema de deployer de um foguete experimental é feito por uma válvula que ejeta a coifa do foguete e aciona uma mola onde está abrigado o satélite. Dessa forma ele ejeta o satélite que deve soltar um paraquedas para aterrissar em segurança. O deployer é responsável por colocar o satélite na altura desejada para que possa fazer as medições desejadas.


```eval_rst
.. image:: assets/estrutura/foguete-deployer.jpg
  :align: center
  :width: 500
..
```

- **Balão Deployer**: Quando a missão é realizada por balão atmosférico o deployer se torna uma estrutura fixa com o sistema do balão atmosférico, ou seja, o satélite retorna ao solo junto com todo o sistema do balão, isso permite que o algumas estruturas do bus do balão pode ser utilizado pelo satélite, dando mais espaço para colocar outros payloads no satélite, no caso do deployer ele em geral já é fornecido pelo lançador de acordo com a missão.


```eval_rst
.. image:: assets/estrutura/balao-deployer.jpg
  :align: center
  :width: 400
..
```