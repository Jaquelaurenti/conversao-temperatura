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