# Trabalho de Docker - Engenharia de Software II

1. Estrutura do projeto
 + Construímos um HTML básico com CSS para um servidor Nginx Docker hospedar

2. Dockerfile para o servidor Nginx
  + Criamos um Dockerfile para criar o arquivo de configuração que descreve os passos necessários para construir uma imagem Docker
  + Nesse Dockerfile, dizemos ao Docker para criar uma imagem com base na imagem base do Nginx e, em seguida, copiar os arquivos HTML e CSS para o diretório padrão do Nginx (/usr/share/nginx/html), onde o servidor web servirá esses arquivos estáticos

3. Construindo a imagem Docker
  + Aqui buildamos a imagem Docker usando o comando `` docker build -t trabalho-docker . ``

<div align="center">
![image](https://github.com/CarolinaSFreitas/docker-trab/assets/99994934/1aa7efb6-cc25-4cba-b5d2-09d9f3b90658)
</div>

4. Executando o container com a imagem criada
 + Após o build fizemos a execução do container para rodar o Nginx com nosso HTML através do comando `` docker run -d -p 8080:80 --name container-trab trabalho-docker ``

<div align="center">
![image](https://github.com/CarolinaSFreitas/docker-trab/assets/99994934/6c59d858-f564-464f-80bb-0b74000a553f)
</div>

Container do Nginx sendo executado com sucesso na porta 8080 definida na criação do container:

<div align="center">
![server](https://github.com/CarolinaSFreitas/docker-trab/assets/99994934/a3624414-ec8f-471e-80c8-70d02c1c9f1b)
</div>

5. 
