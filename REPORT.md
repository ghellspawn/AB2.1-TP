Identificação
=============
-------------
* Página do repositório do trabalho ([Link GitHub](https://github.com/ghellspawn/AB2.1-TP))

* Discente 1

Nome: Gabriel Luiz Leite Souza
Matrícula: 19110984
Distribuição da nota (%): IGUAL

* Discente 2

Nome: Jorge Firmo Soares Neto
Matrícula: 19111158
Distribuição da nota (%): IGUAL

* Discente 3

Nome: Carlos Eduardo Noslin Tenório Galvão
Matrícula: 19110974
Distribuição da nota (%): IGUAL

Resultados
==========
----------
[Gráfico UCP](https://i.imgur.com/cnynuhx.png)
Gráfico relacionado ao uso da UCP do comando "UCP".
 
[Gráfico UCP-MEM 1](https://i.imgur.com/Z5Ri39H.png)
Gráfico relacionado ao uso da UCP do comando "UCP-MEM".
 
[Gráfico UCP-MEM 2](https://i.imgur.com/H5cQHpY.png)
Gráfico relacionado ao uso da memória ram do comando "UCP-MEM".

Discussão
========
--------
## Utilização intensa da UCP:
-----------------------------
Conforme o loop do comando "UCP" começa a ser executado (linha 37-41 do programa), a UCP, partindo de 0% de uso (repouso), começa a ser utilizada. Após o início do processo observa-se um pico do alocamento de uso nas primeiras instâncias (entre os segundos 1 e 2), logo em seguida um leve declínio na sua utilização (entre os segundos 2 e 3), acompanhado de um período de estabilidade (entre os segundos 3 e 7). Ao aproximar-se do tempo limite de 10 segundos, ocorre uma discreta diminuição em seu uso (entre os segundos 7 e 10). O resultado atendeu as expectativas, pois o uso da UCP está diretamente relacionado à exigência da mesma. O resultado atendeu as expectativas, pois o uso da UCP está diretamente relacionado à exigência da mesma, dado que há um loop infinito (linha 39 do programa) na execução do "processo-filho", o qual se manterá em atividade constante, a demandar uma grande quantidade de processamento, de modo contínuo durante a execução de todo o processo. Vale ressaltar que, no momento em que o processador ultrapassa a margem dos 100% ele estará utilizando mais de um núcleo, que será requisitado, de acordo com a necessidade, para a continuidade e fluidez do programa.


## Utilização intensa da UCP e memória:
---------------------------------------
A função malloc (linha 46) foi de suma importância para a execução dessa parte do código. Através dele foi possível fazer o alocamento de memória com sucesso, a fim de, junto ao laço repetitivo (linha 44), extrair uma grande quantidade de memória ram do computador. O gráfico de utilização da memória ram pelo comando “UCP-MEM” possui uma lógica fácil de ser compreendida. O uso da ram começa em zero (no segundo 0) e, conforme os segundos passam e o comando UCP-MEM continua a ser executado, ela cresce rapidamente. A função “malloc” continua alocando memória, até o tempo limite (10 segundos), logo o uso cresce até atingir o limite de tempo. Nesse procedimento, o computador teste (com oito gigas de memória ram) desligou diversas vezes. Pois, para que o computador não “morra”, o número de bytes digitado entre parênteses na função malloc tem que ser muito pequeno. Caso o número seja maior do que o devido (maior do que o usado no código fonte), o computador certamente irá desligar, consequência da alocação exuberante de memória ram pela função “malloc”, fazendo com que toda a memória seja alocada e o computador desligue por falta de armazenamento volátil mínimo requisitado pelo sistema operacional.  

O gráfico de utilização de UCP pelo comando “UCP-MEM” tem um comportamento parecido com o gráfico do comando “UCP”. Podem deduzir-se duas coisas: 1) o uso da memória ram, em conjunto do uso de processamento, não fez a UCP do computador aumentar. Algo que o grupo pensou que iria acontecer, mas não ocorreu. 2) Os laços de repetição dos dois comandos são parecidos e quase iguais. Sendo diferenciados apenas pela existência da função malloc no comando “UCP-MEM”. Como a alocação de memória não mudou no uso de UCP, portanto, sendo os dois laços repetitivos parecidos, o desempenho da UCP tende a ser igual.

