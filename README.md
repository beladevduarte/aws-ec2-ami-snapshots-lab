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
1️⃣ Criação da Instância EC2

SO: Amazon Linux 2

Tipo: t2.micro (Free Tier)

Configurações:

Porta 22 (SSH) liberada

Porta 80 (HTTP) liberada

Volume EBS de 8 GB

📸 

---
2️⃣ Instância em Execução

Após o deploy, a instância entrou em estado Running.

📸 


---
3️⃣ Conexão via SSH e Instalação do Apache

Conexão na instância:
````
ssh -i minha-chave.pem ec2-user@<IP-da-instancia>

sudo yum update -y
sudo yum install httpd -y
sudo systemctl start httpd
sudo systemctl enable httpd
````

---
4️⃣ Criação da AMI

Após personalizar a instância, foi criada uma Amazon Machine Image (AMI) personalizada.

📸 

---
5️⃣ Criação de Snapshot EBS

Snapshot do volume EBS criado como backup e ponto de restauração.

📸 


---
6️⃣ Nova Instância a partir da AMI

Uma nova instância foi lançada com base na AMI personalizada para validar sua integridade.

📸 


📸 

---
Todas as capturas estão disponíveis na pasta images/ do repositório.
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
