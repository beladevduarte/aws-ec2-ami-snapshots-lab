# 🚀 Laboratório AWS - Gerenciamento de Instâncias EC2, AMIs e Snapshots

Este repositório contém a documentação completa do laboratório prático realizado na **AWS (Amazon Web Services)**, com foco em **EC2 (Elastic Compute Cloud)**, **AMIs (Amazon Machine Images)** e **Snapshots EBS**.  

O objetivo foi **consolidar conhecimentos em computação em nuvem**, praticando em um ambiente real e registrando toda a experiência de ponta a ponta.  

---

## 📚 Sumário
- [🎯 Objetivos do Desafio](#-objetivos-do-desafio)
- [🏗 Arquitetura do Laboratório](#-arquitetura-do-laboratório)
- [🔧 Etapas Executadas](#-etapas-executadas)
- [📸 Capturas de Tela](#-capturas-de-tela)
- [🛠 Recursos Utilizados](#-recursos-utilizados)
- [💡 Reflexão Pessoal](#-reflexão-pessoal)
- [✅ Conclusão](#-conclusão)

---

## 🎯 Objetivos do Desafio
- Criar e gerenciar **instâncias EC2** na AWS.  
- Personalizar instâncias com pacotes adicionais (**Apache**).  
- Criar **AMIs personalizadas**.  
- Gerar e gerenciar **Snapshots EBS**.  
- Documentar todo o processo de forma clara e organizada.  

---

## 🏗 Arquitetura do Laboratório
Fluxo do ambiente criado no laboratório:

```mermaid
flowchart TD
    A[Criação da Instância EC2] --> B[Instalação do Apache]
    B --> C[Criação de AMI personalizada]
    C --> D[Criação de Snapshot EBS]
    D --> E[Lançamento de nova instância a partir da AMI]
    D --> F[Validação do Snapshot como backup]
````

🔧 Etapas Executadas


---
1️  Criação da Instância EC2

SO: Amazon Linux 2

Tipo: t2.micro (Free Tier)

Configurações:

Porta 22 (SSH) liberada

Porta 80 (HTTP) liberada

Volume EBS de 8 GB

📸 

---
2️  Instância em Execução

Após o deploy, a instância entrou em estado Running.

📸 


---
3️  Conexão via SSH e Instalação do Apache

Conexão na instância:
````
ssh -i minha-chave.pem ec2-user@<IP-da-instancia>

sudo yum update -y
sudo yum install httpd -y
sudo systemctl start httpd
sudo systemctl enable httpd
````

---
4️  Criação da AMI

Após personalizar a instância, foi criada uma Amazon Machine Image (AMI) personalizada.

📸 

---
5️  Criação de Snapshot EBS

Snapshot do volume EBS criado como backup e ponto de restauração.

📸 


---
6️  Nova Instância a partir da AMI

Uma nova instância foi lançada com base na AMI personalizada para validar sua integridade.

📸 


📸 

---
 📸 Todas as capturas estão disponíveis na pasta images/ do repositório.
Incluem:

Criação da instância

Instância em execução

Apache configurado

AMI criada

Snapshot do volume

Nova instância a partir da AMI

---
🛠 Recursos Utilizados

AWS EC2 – Computação em nuvem

Amazon Machine Images (AMI) – Criação de imagens personalizadas

Amazon EBS Snapshots – Backup de volumes

Apache HTTP Server – Servidor Web

SSH – Acesso remoto seguro

---
💡 Reflexão Pessoal

Este laboratório me permitiu:

Consolidar conceitos essenciais da AWS.

Entender na prática como funcionam AMIs e Snapshots.

Criar um ambiente reprodutível, escalável e seguro.

Aumentar minha familiaridade com o fluxo Deploy → Configuração → Backup → Restauração.

---
✅ Conclusão

Este projeto reforçou habilidades práticas em Infraestrutura em Nuvem e Gerenciamento de Recursos AWS, 
preparando o caminho para cenários mais avançados em arquitetura cloud, automação e alta disponibilidade.

📌 Repositório criado para fins de estudo e prática profissional.

graph TD
    subgraph Plataforma DIO / Aluno
        A[Aluno / Usuário] -->|Requisição Web/Upload| B(Amazon API Gateway);
        B -->|Invoca| C1(AWS Lambda: Processador de Entrada);
    end

    subgraph Fluxo de Conteúdo e Documentação
        C1 -->|Upload de Anotação| D1(Amazon S3: Bucket Conteúdo);
        D1 -->|Event: s3:ObjectCreated| C2(AWS Lambda: Processador de Anotações);
        C2 --> E(Amazon DynamoDB: Tabela Metadados);
    end

    subgraph Gerenciamento EC2 (Desafio Técnico)
        F1(Amazon CloudWatch: Evento Agendado) --> C3(AWS Lambda: Gerenciador EC2/EBS);
        C3 -->|Monitoramento / Ação| G[Amazon EC2: Instância de Estudo];
        G --> H(Amazon EBS: Volume);
        C3 -->|EC2 API: CreateSnapshot| D2(Amazon S3: Bucket Backups);
    end

    subgraph Monitoramento
        C1 --> L[CloudWatch Logs];
        C2 --> L;
        C3 --> L;
    end

    style A fill:#a9c5ec,stroke:#333,stroke-width:2px
    style G fill:#f9f,stroke:#333,stroke-width:2px
    style B fill:#ffd966,stroke:#333,stroke-width:2px
    style C1 fill:#b1e1ff,stroke:#333,stroke-width:2px
    style C2 fill:#b1e1ff,stroke:#333,stroke-width:2px
    style C3 fill:#b1e1ff,stroke:#333,stroke-width:2px
    style D1 fill:#92d050,stroke:#333,stroke-width:2px
    style D2 fill:#92d050,stroke:#333,stroke-width:2px
    style E fill:#f37f39,stroke:#333,stroke-width:2px
    style F1 fill:#a6a6a6,stroke:#333,stroke-width:2px
    style H fill:#c5d9f1,stroke:#333,stroke-width:2px
    style L fill:#93c47d,stroke:#333,stroke-width:2px

    title Arquitetura AWS: Gerenciamento EC2 & Estudo DIO Challenge
