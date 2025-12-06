🚀 Visão Geral do Projeto

Este projeto consiste em uma aplicação web simples desenvolvida com Flask (Python), empacotada em um container Docker e implantada em um cluster Kubernetes usando Minikube. O objetivo é demonstrar os conceitos de containerização, orquestração e auto-recuperação de pods.

📁 Estrutura de Arquivos

k8s-lab-nginx/
├── app.py
├── requirements.txt
├── Dockerfile
├── deployment.yaml
└── service.yaml

🧱 Etapas para Executar o Projeto

1. Criar a imagem Docker

docker build -t minha-app .

2. Rodar localmente (opcional)

docker run -p 5000:5000 minha-app

Acesse: http://localhost:5000

3. Carregar a imagem no Minikube

minikube image load minha-app

4. Aplicar os manifests Kubernetes

kubectl apply -f deployment.yaml
kubectl apply -f service.yaml

5. Obter o IP do Minikube

minikube ip

6. Acessar a aplicação via navegador

http://<IP-do-minikube>:30081

📄 Explicação dos Arquivos

app.py

Código da aplicação Flask que responde na rota / com uma mensagem simples.

requirements.txt

Lista de dependências Python (neste caso, apenas flask).

Dockerfile

Define como a imagem Docker será construída:

Usa Python 3.9 slim

Instala dependências

Copia o código da aplicação

Executa o servidor Flask

deployment.yaml

Cria um Deployment no Kubernetes com 2 réplicas da aplicação, usando a imagem minha-app.

service.yaml

Cria um Service do tipo NodePort, expondo a aplicação na porta 30081 do Minikube.

🧪 Testes Recomendados

Excluir um pod manualmente para testar auto-recuperação:

kubectl delete pod <nome-do-pod>
kubectl get pods -w

Escalar réplicas:

kubectl scale deployment minha-app-deployment --replicas=5

Ver logs:

kubectl logs -l app=minha-app

📦 Publicar no GitHub

git init
git add .
git commit -m "Minha aplicação Flask com Docker e Kubernetes"
git branch -M main
git remote add origin https://github.com/<seu-usuario>/<nome-repo>.git
git push -u origin main

✅ Conclusão

Este projeto mostra como empacotar uma aplicação Flask com Docker, implantá-la em Kubernetes com Minikube e expô-la via NodePort. Ideal para aprender os fundamentos de DevOps e orquestração de containers.
