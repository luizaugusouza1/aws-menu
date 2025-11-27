# 🍽️ Projeto SaaS de Delivery Online na AWS  
### (Cardápio Virtual + Pedidos via WhatsApp + Infraestrutura Automatizada com CloudFormation)

Este repositório contém toda a infraestrutura, código e recursos necessários para implantar um **sistema SaaS de delivery online** baseado em “cardápio virtual”, onde restaurantes se cadastram, criam seu ambiente próprio e os clientes finalizam pedidos diretamente pelo WhatsApp.

O projeto demonstra a migração completa de uma aplicação real — antes hospedada em uma VPS — para uma arquitetura **100% AWS**, utilizando **CloudFormation**, **EC2**, **RDS**, **Route 53**, **Load Balancer** e práticas modernas de **Infraestrutura como Código (IaC)**.

---

## 🎯 1. Objetivo do Projeto

Construir e publicar um sistema SaaS de delivery onde:

- Restaurantes criam sua conta.
- Personalizam seu cardápio online.
- Clientes acessam o link do restaurante.
- Realizam pedidos → envio automático via WhatsApp.
- Restaurantes acessam relatórios, editam itens e banners.

Além disso, demonstrar domínio de:

- Arquitetura AWS  
- DevOps e Automação  
- IaC com CloudFormation  
- Redes, Segurança e Boas Práticas  
- Migração de Aplicações tradicionais (VPS → AWS)

---

## 🏗️ 2. Arquitetura da Solução

A infraestrutura foi totalmente desenvolvida com **AWS CloudFormation**, permitindo criação rápida, automatizada e versionada.

### 🔹 **Componentes Principais**

- **VPC Dedicada**
  - /16 com isolamento total
  - Subnets públicas e privadas
  - Internet Gateway
  - Tabelas de rota separadas

- **EC2 (Linux – Ubuntu)**
  - Hospeda o sistema SaaS
  - Scripts User Data automatizam:
    - Instalação do servidor web
    - Atualizações
    - Configuração inicial
  - Segurança via Security Groups

- **RDS MySQL**
  - Banco de dados totalmente gerenciado
  - Segurança por SG
  - Conexão direta com a aplicação

- **Elastic Load Balancer (ALB)**
  - Balanceamento de tráfego
  - Certificado SSL

- **Route 53**
  - Configuração do domínio .NET
  - Registros para apontamento do ALB

- **FTP (migração inicial)**
  - Upload do sistema para a EC2
  - Configurações ajustadas para acesso ao RDS

---

## ⚙️ 3. Infraestrutura Automatizada (CloudFormation)

O template cria automaticamente:

- VPC  
- Sub-redes públicas/privadas  
- Gateway de Internet  
- Tabelas de rota  
- Security Groups  
- Instância EC2 Ubuntu  
- Banco RDS MySQL  
- Balanceador de carga  
- Associações DNS via Route 53  

Scripts User Data realizam toda a preparação do servidor.

---

## 🚀 4. Migração da Aplicação da VPS para AWS

A aplicação originalmente estava em:

- VPS contratada
- Upload via FTP
- Banco de dados local
- Domínio configurado manualmente

O projeto migrou tudo para AWS:

✔ Aplicação → EC2  
✔ Banco local → RDS  
✔ FTP → GitHub + CodePipeline (opcional)  
✔ Domínio externo → Route 53  
✔ HTTPS automático via certificado

Após o deploy, o sistema já estava **totalmente funcional** na AWS.

---

## 📹 5. Resumo da Apresentação (26/11/2025)

Durante a reunião, apresentei:

### 🔸 **Demonstração do SaaS**
- Cadastro de restaurante
- Edição de cardápio
- Pedido enviado automaticamente ao WhatsApp
- Relatórios e administração

### 🔸 **Infraestrutura AWS**
- Template CloudFormation com toda a estrutura
- Duas sub-redes (pública/privada)
- Gateway e rotas configuradas
- EC2 Linux com User Data automatizando a instalação
- Banco RDS criado no deploy
- Load Balancer configurado
- Domínio configurado via Route 53 + SSL

### 🔸 **Processo de Deploy**
- Template enviado para CloudFormation
- Criação automática da VPC e recursos
- Subida da EC2 + EIP + ALB
- Upload dos arquivos via FTP
- Ajustes para apontar para o RDS

### 🔸 **Conclusão**
> Migração 100% concluída  
> Sistema funcionando perfeitamente na AWS  
> Restaurantes podem:
> - Gerenciar itens  
> - Alterar banners  
> - Consultar relatórios  
> - Receber pedidos via WhatsApp  

---

## 📚 6. Tecnologias Utilizadas

### 🟦 AWS
- EC2  
- RDS MySQL  
- VPC  
- Subnets  
- Route 53  
- ALB  
- Security Groups  
- IAM  
- CloudFormation
- Certificate Manager

### 🟧 Infraestrutura e Desenvolvimento
- YAML (IaC)  
- Bash (User Data)  
- GitHub  
- VS Code  
- FTP (migração inicial)  

### 🟩 Aplicação SaaS
- PHP / HTML / CSS / JavaScript  
- Sistema multi-restaurante  

---

## 📘 7. Aprendizados

- Construção de ambientes AWS do zero  
- Automação com IaC  
- Rede e segurança (subnets, SG, IGW, rotas)
- Banco de dados gerenciado (RDS)
- Load Balancer + SSL  
- Migração de VPS para Cloud  
- Organização e versionamento com GitHub  

---

## 🔮 8. Próximos Passos

- Criar pipeline CI/CD (CodePipeline ou GitHub Actions)  
- Colocar armazenamento de imagens no S3 + CloudFront  
- Criar Auto Scaling Group  
- Migrar logs para CloudWatch  
- Criar monitoramento com Zabbix/Grafana  

---

## 📎 9. Prints e Evidências  
<table>
  <tr>
    <td><img src="./images/images%20(1).png" width="300px"/></td>
    <td><img src="./images/images%20(2).png" width="300px"/></td>
    <td><img src="./images/images%20(3).png" width="300px"/></td>
  </tr>
  <tr>
    <td><img src="./images/images%20(4).png" width="300px"/></td>
    <td><img src="./images/images%20(5).png" width="300px"/></td>
    <td><img src="./images/images%20(6).png" width="300px"/></td>
  </tr>
  <tr>
    <td><img src="./images/images%20(7).png" width="300px"/></td>
    <td></td>
    <td></td>
  </tr>
</table>

---

## 📺 10. Vídeo da Implantação 

Clique para assistir o deploy completo do projeto na AWS �

[▶ Assista no YouTube](https://youtu.be/hyDsMO7DlLc)
<table>
  <tr>
    <td><img src="./images/images%20(0).png" width="300px"/></td>
  </tr>
</table>

---

## 👨‍💻 Autor  
**Luiz Augusto Souza Inhesta**  
Cloud | Infra | DevOps | AWS | IaC  
