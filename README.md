# Minha aplicação Flask com Docker e Kubernetes

Este projeto demonstra como criar uma aplicação simples em **Flask**, empacotá-la em um container **Docker** e implantá-la em um cluster **Kubernetes** usando **Minikube**.

## Estrutura do projeto
- `app.py` → código da aplicação Flask
- `requirements.txt` → dependências Python
- `Dockerfile` → instruções para criar a imagem Docker
- `deployment.yaml` → manifesto Kubernetes para o Deployment
- `service.yaml` → manifesto Kubernetes para o Service

## Como executar

1. **Construir a imagem Docker**
   ```bash
   docker build -t minha-app .
