## Criar a imagem docker
Entar no diretório src e executar o comando abaixo
```sh
docker build -t jaquelaurenti/conversao-temperatura-curso:v1 .
```
obs: não esquecer do "."
## Criar container a partir da imagem
```sh
docker run -d -p 8080:8080 jaquelaurenti/conversao-temperatura-curso:v1
````


## Enviar a imagem para o docker hub
Após executar os comandos acima
```sh
docker build -t jaquelaurenti/conversao-temperatura-curso:v1 .
docker tag jaquelaurenti/conversao-temperatura-curso:v1 jaquelaurenti/conversao-temperatura-curso:latest
docker login
docker push jaquelaurenti/conversao-temperatura-curso:v1
docker push jaquelaurenti/conversao-temperatura-curso:latest
```

## Iniciar o k3d e executar o Deployment
```sh
k3d cluster create meucluster -p "8080:30000@loadbalancer"
cd k8s
kubectl apply -f deployment.yaml
```