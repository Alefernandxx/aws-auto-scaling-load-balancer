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








