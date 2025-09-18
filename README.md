# aws-auto-scaling-load-balancer

Objetivo: Resumir o que são Auto Scaling, Load Balancer e as regras de Scaling Up e Down, também explicar o que aprendemos e o passo-a-passo de cada serviço.

1) Auto Scaling:

É um serviço da AWS que ajusta automaticamente a quantidade de instâncias EC2 de acordo com a demanda, e tem como objetivo garantir performance (quando a carga aumenta) e reduzir custos (quando a carga cai).

O que aprendemos:

Ele trabalha junto com CloudWatch (para métricas e alarmes).

Pode adicionar (scale out/up) ou remover instâncias (scale in/down).

Garante alta disponibilidade e elasticidade.

