# aws-auto-scaling-load-balancer

Objetivo: Resumir o que são Auto Scaling, Load Balancer e as regras de Scaling Up e Down, também explicar o que aprendemos e o passo-a-passo de cada serviço.

🖥️ Auto Scaling:

É um serviço da AWS que ajusta automaticamente a quantidade de instâncias EC2 de acordo com a demanda, e tem como objetivo garantir performance (quando a carga aumenta) e reduzir custos (quando a carga cai).

Passo-a-passo:

1) Criar um Launch Template (modelo da instância)

1.1) AMI: escolha a imagem (ex: Amazon Linux 2, Ubuntu).
<img width="833" height="266" alt="image" src="https://github.com/user-attachments/assets/1424577d-72b9-45ca-9867-1af415db14a5" />

1.2) Instance type: ex t3.micro
<img width="1234" height="215" alt="image" src="https://github.com/user-attachments/assets/d0a21e87-c756-475f-8b31-80621427e6f5" />

1.3) ⚠️IMPORTANTE⚠️ Security groups: associe um SG que permita tráfego necessário (HTTP/HTTPS).

1.4) User data: cole o script de bootstrap (instala dependências, registra app, configura health endpoint).
<img width="796" height="325" alt="image" src="https://github.com/user-attachments/assets/4e83679e-b41f-4607-a9e1-f0741744aade" />

1.5) Criar modelo de execução.

1.6) Definir o Auto Scaling Group (ASG)

1.7) Configurar regras de scaling (quando aumentar/diminuir).

1.8) Associar ao Load Balancer (opcional, mas recomendado).

🖥️ Load Balancer:

É um serviço que distribui automaticamente o tráfego entre várias instâncias EC2, e tem como objetivo evitar sobrecarga em uma única instância, aumentar tolerância a falhas.

Passo-a-passo:

2) Criar um Load Balancer no console.

2.1) Definir Listeners (ex: HTTP 80, HTTPS 443).

2.2) Criar Target Groups (instâncias EC2, containers, etc).

2.3) Associar ao Auto Scaling Group.

🖥️ Regras de Scaling (Up e Down):

Scaling Up/Out: Adicionar instâncias quando a demanda aumenta.

Scaling Down/In: Remover instâncias quando a demanda diminui.

Passo-a-passo:

3) Definir métricas no CloudWatch (ex: CPU > 70% por 5 minutos → scale up).

3.1) Criar uma política de scaling (ex: adicionar 1 instância).

3.2) Definir o oposto para scale down (ex: CPU < 30% por 5 minutos → remover 1 instância).

3.3) Testar a aplicação sob carga para validar as regras.

4) O que aprendi: 

Durante esse projeto, aprendi a criar e configurar um Auto Scaling Group a partir de um Launch Template, garantindo que as instâncias EC2 fossem gerenciadas automaticamente. Também configurei um Load Balancer e associei as instâncias através de um Target Group, entendendo melhor como ele distribui as requisições apenas para aquelas que estão saudáveis.

Outro ponto importante foi a definição das regras de scaling, tanto para aumentar (scaling up) quanto para reduzir (scaling down) a quantidade de instâncias com base em métricas do CloudWatch. Isso mostrou na prática como o ajuste automático ajuda a manter um equilíbrio entre performance e custo.

Por fim, fiz testes de carga para validar se as regras criadas realmente funcionavam, e isso me deu uma visão clara de como esses recursos trabalham juntos para deixar a aplicação mais estável e escalável.







