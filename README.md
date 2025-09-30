# aws-ec2-ami-snapshots-lab
Laboratório AWS - Gerenciamento de Instâncias EC2, AMIs e Snapshots

# 🚀 Desafio de Projeto - Gerenciamento de Instâncias EC2 na AWS  

Este repositório contém a documentação do **laboratório prático de EC2 na AWS**, com foco em **AMIs (Amazon Machine Images)** e **Snapshots EBS**.  
O objetivo foi **consolidar os conhecimentos adquiridos** em sala, praticando em um ambiente real e registrando a experiência de ponta a ponta.  

---

## 📚 Sumário
- [Objetivos do Desafio](#-objetivos-do-desafio)
- [Arquitetura do Laboratório](#-arquitetura-do-laboratório)
- [Etapas Executadas](#-etapas-executadas)
- [Capturas de Tela](#-capturas-de-tela)
- [Recursos Utilizados](#-recursos-utilizados)
- [Reflexão Pessoal](#-reflexão-pessoal)
- [Conclusão](#-conclusão)

---

## 🎯 Objetivos do Desafio
- Criar e gerenciar instâncias EC2 na AWS.  
- Personalizar instâncias com pacotes adicionais (Apache).  
- Criar **AMIs personalizadas**.  
- Gerar e gerenciar **Snapshots EBS**.  
- Documentar todo o processo de forma clara e organizada.  

---

## 🏗 Arquitetura do Laboratório
Fluxo seguido no laboratório:  

1. Criação de uma instância EC2.  
2. Personalização da instância com Apache.  
3. Criação de AMI personalizada.  
4. Criação de Snapshot do volume EBS.  
5. Lançamento de nova instância a partir da AMI.  
6. Validação do Snapshot como backup.  

📸 *(Inserir diagrama ou print do Console AWS mostrando os recursos criados)*  

---

## 🔧 Etapas Executadas

### 1️⃣ Criação da Instância EC2
- Sistema operacional: **Amazon Linux 2**  
- Tipo de instância: **t2.micro (Free Tier)**  
- Configurações principais:
  - Porta 22 (SSH) liberada  
  - Porta 80 (HTTP) liberada  
- Volume EBS padrão de 8 GB  

📸 *Print da instância criada*  

---

### 2️⃣ Conexão via SSH e Instalação do Apache
Comando para acessar:  
```bash
ssh -i minha-chave.pem ec2-user@<IP-da-instancia>
