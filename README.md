# 🐳 Atividade de Docker - Engenharia de Software II

### Grupo: Carolina Freitas, Gabriel Mendes, Júlia Hallal, Maria Antônia Soares e Rodrigo Silva

1. **Estrutura do projeto**
 + Construímos um HTML básico com CSS para um servidor Nginx hospedar

2. **Dockerfile para o servidor Nginx**
  + Criamos um Dockerfile para definir o arquivo de configuração que descreve os passos necessários para construir uma imagem Docker
  + Nesse Dockerfile, pedimos ao Docker para criar uma nova imagem baseada na imagem oficial do Nginx e, em seguida, copiar os arquivos HTML e CSS para o diretório padrão do Nginx (/usr/share/nginx/html), onde o servidor web servirá esses arquivos estáticos

3. **Construindo a imagem Docker**
  + Aqui buildamos a imagem Docker usando o comando ``docker build -t trabalho-docker .``

![image](https://github.com/CarolinaSFreitas/docker-trab/assets/99994934/1aa7efb6-cc25-4cba-b5d2-09d9f3b90658)

4. **Executando o container com a imagem criada**
 + Após o build fizemos a execução do container para rodar o Nginx com nosso HTML através do comando ``docker run -d -p 8080:80 --name container-trab trabalho-docker``

![image](https://github.com/CarolinaSFreitas/docker-trab/assets/99994934/6c59d858-f564-464f-80bb-0b74000a553f)

Container do Nginx sendo executado com sucesso na porta 8080 definida na criação do container:
![server](https://github.com/CarolinaSFreitas/docker-trab/assets/99994934/0ce39527-3a5c-4117-ae6e-5bd20ce8323f)

5. **Criando um Docker Compose**
 + O arquivo ``docker-compose.yml`` tem como principais configurações criar o serviço de banco de dados usando MySQL, com persistência de dados e capacidade de reinicialização sempre que houver falhas. Ele também criará o container do Nginx junto ao banco de dados

6. **Subindo o Docker Compose**
 + Usando o comando ``docker-compose up -d`` subimos o Compose de forma detachada/em segundo plano 

![image](https://github.com/CarolinaSFreitas/docker-trab/assets/99994934/3d24fcf6-edaf-4f6d-9556-36c8dde0b915)

+ Acessando novamente a porta 8080 do localhost (http://localhost:8080/) será possível acessar o Nginx com o HTML 
+ Para acessar o container do MySQL como root basta usar os comandos: ``docker-compose exec db mysql -u root -p`` e digitar a senha definida pro root no arquivo do Compose
   
  ![image](https://github.com/CarolinaSFreitas/docker-trab/assets/99994934/5b055952-9028-4415-b53c-5925e7d5d1d1)

+ Se for acessar como usuário aluno (também definido no docker-compose.yml), usar: ``docker-compose exec db mysql -u aluno -p``

![image](https://github.com/CarolinaSFreitas/docker-trab/assets/99994934/b7d9f810-7dc2-4945-9448-2287d19b8698)


  
