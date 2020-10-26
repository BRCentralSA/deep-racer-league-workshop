************************************************
Entendendo Reinforcement Learning
************************************************

Nesta etapa do Workshop entenderemos o que é Reinforcement Learning e como ele é aplicado no DeepRacer

O que é Reinforcement Learning?
-----------------------------------------

Reinforcement learning (RL) é um tipo de machine learning, onde um agente explora um ambiente e aprende como performar as tasks desejadas ganhando pontos caso o resultado seja bom e perdendo pontos caso o resultado seja ruim.

Um modelo de Reinforcement Learning irá aprender baseado na sua experiência e com o tempo será capaz de identificar quais ações geram as melhores recompensas.

.. image:: _static/reinforcment_learning/deep_racer_01.png

Como o AWS DeepRacer aprende a dirigir sozinho?
------------------------------------------------

No Reinforcement learning, um agente dentro de um ambiente tem um objetivo de maximizar o ganho, dessa maneira o agente toma açoes baseado no estado do ambiente e retorna uma recompensa.

.. note:: O Apredizado no Reinforcement Learning é por tentativa e erro, inicialmente tomando ações de maneira aleatória.

**Agente**

.. image:: _static/reinforcment_learning/agent.png

**Ambiente**

.. image:: _static/reinforcment_learning/ambiente.png

**Ação**

Uma ação é o movimento realizado pelo agente no estado atual, para o AWS DeepRacer uma ação corresponde a mover-se em uma velocidade, ângulo e direção particulares. 

**Recompensa**

É a pontuação dada como feedback para o agente quando ele toma uma ação em um determinado estado.

.. note:: No AWS DeepRacer a recompensa é realizada utilizando uma reward function, criaremos nossa primeira função mais a frente no Workshop 

Como treinar um modelo de Reinforcement Learning?
--------------------------------------------------

**Um ambiente simples**

Abaixo temos uma demonstração de um ambiente simples onde o objetivo é o carrinho (agente) ir do início até a linha de chegada.

.. image:: _static/reinforcment_learning/sample_environment.png

**Pontuação**

Como o nosso Objetivo é que o carrinho vá de um lado para o outro percorrendo o centro, em cada quadrado adicionamos uma pontuação, pelo meio a pontuação é maior já pelo caminho indesejado é menor.

Dessa maneira o objetivo é que baseado em uma quantidade X de **iterações** o nosso agente seja capaz de escolher o melhor caminho.

.. image:: _static/reinforcment_learning/score_environment.png

Baseado nas iterações do agente, ele vai adiquirindo cada vez mais experiência, aprendendo a ficar no centro da pista assim ganhando mais pontos.

.. image:: _static/reinforcment_learning/pista01.png 

.. image:: _static/reinforcment_learning/grafico01.png

Quanto mais tempo de treinamento do modelo e a estratégia de função de recompensa o agente é capaz de atingir o destino de forma mais rápida

.. image:: _static/reinforcment_learning/pista02.png 

.. image:: _static/reinforcment_learning/grafico02.png

Paramêtros de uma função de recompensa
--------------------------------------------------

No AWS DeepRacer a função de recompensa é uma função em Python com um certo número de paramêtros que descrevem o estado atual e retorna uma recompensa númerica

**Vamos explorar alguns desses paramêtros abaixo**
