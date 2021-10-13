# 1 - Clone o repositório usando o comando:

git clone  https://github.com/AlessandroVicent/Topico.git

# 2 - Entre na pasta  e copie o arquivo env-example para .env.

cp env-example .env

# 3 - Rode seu container:

docker-compose up -d

# 4 - Adicione os domínios no arquivo de hosts do windows.

127.0.0.1 localhost

127.0.0.1 api.dev

# 5 - Abra no navegador

http://localhost

http://api.dev

# 6 - Acessar o shell do container:

winpty docker exec -it nginx bash

winpty docker exec -it postgresql bash

# 7 - Acessar o banco de dados dentro do container Postgresql

psql default default

# 8 - Comandos básicos para utilizar o banco de dados

\l;

CREATE DATABASE teste;

\connect teste;

\dt;

CREATE TABLE pessoa (id serial primary key, nome varchar(60) not null);

INSERT INTO pessoa(nome) VALUES ('carolina');

INSERT INTO pessoa(nome) VALUES ('jose');

INSERT INTO pessoa(nome) VALUES ('lucas');

INSERT INTO pessoa(nome) VALUES ('janaina');
