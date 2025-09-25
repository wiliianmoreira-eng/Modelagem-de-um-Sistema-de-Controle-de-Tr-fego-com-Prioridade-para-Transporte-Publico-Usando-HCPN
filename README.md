# Segundo projeto da disciplina Sistemas a eventos discretos
## Integrantes
- Marcus Vinícius de Medeiros - 121110400
- Willian Santos Moreira - 121110532
- Ygor de Almeida Pereira - 121110166

## Descrição do problema
- Modelagem de um Sistema de Controle de Tráfego com Prioridade para Transporte Público Usando Redes de Petri Coloridas Hierárquicas (HCPN)
  - O principal objetivo do trabalho é desenvolver um modelo em Redes de Petri Coloridas Hierárquicas (HCPN) capaz de simular e analisar o funcionamento de um sistema de controle de tráfego, explorando recursos de hierarquia, cores e temporização característicos de sistemas a eventos discretos. De forma mais específica, busca-se modelar o comportamento de uma interseção com múltiplas faixas, considerando mecanismos de priorização para o transporte público. Para isso, a hierarquia será utilizada de modo a modularizar o sistema em diferentes subsistemas, como módulos dedicados ao controle de semáforos, à detecção de veículos e ao gerenciamento de filas.

## Esquemático do sistema

imagem

## Variáveis e conjunto de cores do sistema
<p align="center">
  <img src="imagens/var.png" alt="Variáveis e colsets do sistema" width="300"/>
  <br/>
  <em>Figura 1 - Variáveis e colsets do sistema</em>
</p>
É importante explicar algumas variáveis essenciais do projeto com a finalidade de ser mais fácil o entedimento:

- val limitVeh = 8:
  - Define um valor de 8 para a quantidade de veículos que passam no semáforo quando ele estiver verde;
- INT e INT_s:
  - Define inteiros com acompanhamento de delay e numerais inteiros, respectivamente;
- *VTYPE*
  - Define o tipo de carro;
- VEH
  - Define um conjunto de variáveis do produto de (inteiro | tipo de veículo | tempo). Com a finalidade de monitorar a quantidade gerada, o tipo de veículo e o tempo que ele foi gerado;
- Função *makeVeh*
  - Cria justamemnte um valor do tipo veh;
- Função *expTime*
  - Função criada com o objetivo de gerar aleatoriamente veículos para simulação mais realista no modelo; 
## Modelo no *CPN Tools*

Na figura 2 pode-se ver uma visão geral na página principal do sistema, sendo ele modularizado e com uma fácil visualização e interpretação do modelo.
<p align="center">
  <img src="imagens/sistema.png" alt="Variáveis e colsets do sistema" width="300"/>
  <br/>
  <em>Figura 2 - Visão geral do sistema</em>
</p>

### Gera_NS e Gera_LO
A figura 3 mostra a lógica usada para a geração de veículos, onde o lugar e a transição superior geram carros e a inferior gera ônibus. 
<p align="center">
  <img src="imagens/gera.png" alt="Variáveis e colsets do sistema" width="300"/>
  <br/>
  <em>Figura 3 - Geração de veículos </em>
</p>

Dessa forma, é gerado ciclicamente ambos os veículos e passa pela função makeVeh para obter as informações do veículo, que será utilizado posteriormente para a definição de preferencia. A mesma lógica de cores e temporização é definido em ambos os semáforos (Norte - Sul e Leste - Oeste), mas com lógicas invertidas.
 
### Semáforos

A figura 4 mostra toda a lógica implementada do semáforo, com a mudança padrão das cores do semáforo como também a prioridade quando tiver ônibus na fila.
<p align="center">
  <img src="imagens/Semáforo.png" alt="Variáveis e colsets do sistema" width="450"/>
  <br/>
  <em>Figura 4 - Semáforo </em>
</p>




