# Configuração Container Nginx

1. Exposição de porta:

80

2. Volume:

Aplicação: htdocs -> /var/www/html

Logs: nginx/logs -> /var/log/nginx

Virtual Host: nginx/sites -> /etc/nginx/conf.d

3. Virtual Host

Criação do vhost modelo http://api.dev (vhost modificável)

# Configuração Container Postgresql

1. Exposição de porta:

5432

2. Volume:

Aplicação: postgresql/data -> /var/lib/postgresql/data

3. Configuração para conexão

POSTGRES_DB = default

POSTGRES_USER = default

POSTGRES_PASSWORD = secret

POSTGRES_PORT = 5432

# Instruções de Uso

1. Clone o repositório usando o comando:

git clone  https://github.com/AlessandroVicent/Topico.git

2. Entre na pasta Topico e copie o arquivo env-example para .env.

cp env-example .env

3. Rode seu container:

docker-compose up -d

4. Adicione os domínios no arquivo de hosts do windows.

127.0.0.1 localhost

127.0.0.1 api.dev

5. Abra no navegador

http://localhost

http://api.dev

6. Acessar o shell do container:

winpty docker exec -it nginx bash

winpty docker exec -it postgresql bash

7. Acessar o banco de dados dentro do container Postgresql

psql default default

8. Comandos básicos para utilizar o banco de dados

\l;

CREATE DATABASE teste;

\connect teste;

\dt;

CREATE TABLE pessoa (id serial primary key, nome varchar(60) not null);

INSERT INTO pessoa(nome) VALUES ('carolina');

INSERT INTO pessoa(nome) VALUES ('jose');

INSERT INTO pessoa(nome) VALUES ('lucas');

INSERT INTO pessoa(nome) VALUES ('janaina');
