#  Deploy de Aplicação Node.js na AWS ECS com Terraform e CI/CD

Deploy automatizado de uma aplicação Node.js containerizada utilizando AWS ECS Fargate, Terraform e CI/CD com GitHub Actions.

O projeto foi desenvolvido com foco em práticas DevOps modernas, utilizando Infraestrutura como Código (IaC), containers Docker, automação de deploy e monitoramento centralizado via CloudWatch Logs.

---

#  Estrutura do Projeto

```bash
├── app/
│   ├── app.js
│   ├── package.json
│   └── Dockerfile
│
├── terraform/
│   ├── ecs.tf
│   ├── vpc.tf
│   ├── variables.tf
│   └── outputs.tf
│
└── .github/
    └── workflows/
```

---

#  Arquitetura

```text
GitHub Actions
       │
       ▼
Build Docker Image
       │
       ▼
Amazon ECR
       │
       ▼
Amazon ECS Fargate
       │
       ▼
CloudWatch Logs
```

---

#  Tecnologias Utilizadas

- AWS ECS Fargate
- AWS ECR
- AWS CloudWatch Logs
- AWS VPC
- Terraform
- Docker
- Node.js
- GitHub Actions

---

#  Infraestrutura Provisionada com Terraform

Toda a infraestrutura foi criada automaticamente via Terraform.

## Recursos provisionados

- VPC
- Subnets públicas
- Internet Gateway
- Route Tables
- Security Groups
- ECS Cluster
- ECS Task Definition
- ECS Service
- IAM Roles
- CloudWatch Log Group
- Amazon ECR Repository

Nenhum recurso foi criado manualmente no console AWS.

---

#  Aplicação Containerizada

A aplicação Node.js foi empacotada utilizando Docker.

## Build local

```bash
docker build -t node-app ./app
```

---

#  Deploy no Amazon ECS Fargate

A imagem Docker é enviada para o Amazon ECR e executada no ECS Fargate.

## Características

- Deploy serverless
- Escalabilidade automática
- Sem gerenciamento de EC2
- Integração com CloudWatch Logs

---

#  Monitoramento com CloudWatch

Os logs da aplicação são enviados automaticamente para o CloudWatch Logs através da configuração do ECS Task Definition.

## Exemplo de configuração

```json
"logConfiguration": {
  "logDriver": "awslogs",
  "options": {
    "awslogs-group": "/ecs/node-app",
    "awslogs-region": "us-east-1",
    "awslogs-stream-prefix": "ecs"
  }
}
```

## Benefícios

- Monitoramento em tempo real
- Visualização centralizada de logs
- Troubleshooting da aplicação
- Observabilidade da infraestrutura

---

#  CI/CD com GitHub Actions

O projeto utiliza GitHub Actions para automação completa do deploy.

## Pipeline automatizada

- Build da aplicação
- Build da imagem Docker
- Push para o Amazon ECR
- Atualização automática do ECS Service


---

#  Objetivos do Projeto

Este projeto foi criado para praticar:

- Infraestrutura como Código (IaC)
- Containers Docker
- Deploy em ECS Fargate
- Provisionamento AWS com Terraform
- Automação CI/CD
- Observabilidade com CloudWatch
- Boas práticas DevOps

---

#  Conhecimentos Aplicados

- Terraform resources
- ECS Task Definition
- ECS Service
- Docker build e push
- Integração ECR + ECS
- GitHub Actions
- IAM Roles
- Networking AWS
- Logging centralizado


# Autor

Rafael Ferreira Neves

---

#  Licença

Projeto desenvolvido para fins educacionais e portfólio DevOps/Cloud.
