##### Essa apostila é pra você que quer se aventurar em Laravel.

### Instalando Laravel 

## Instalando via laravel installer
	Composer global require “laravel/instaler”

* Para criar o projeto: 

	laravel new blog

## Instalando via Composer Create-Project

* Faça o download do composer https://getcomposer.org/

* Para criar o projeto:

	composer create-project --prefer-dist laravel/laravel <nome do projeto>

## Rodando com Laravel 

* Abra uma nova janela de seu terminal, entre na pasta do projeto e digite o comando
	php artisan serve
* A partir disto seu servidor estará rodando no endereço localhost:8000

* Nos arquivos do seu projeto laravel você encontrará o .env o qual você deverá configurar antes de dar o comando php artisan serve, caso você configure o .env depois de iniciar o server é só renincia-lo.

* O que está circulado em vermelho indica a url que está rodando seu projeto laravel
* DB_PORT é a porta do seu banco
* DB_DATABASE é o nome do banco que vai rodar esse projeto
* DB_USERNAME é o usuário do banco
* DB_PASSWORD é a senha para entrar no banco

## Entendo a estrutura do Laravel..
* Em App/Http você encontrará a pasta controllers, nela ficam todas as Controllers da sua app, é recomendado que você entenda o que é MVC antes de prosseguir.
* Por padrão o Laravel já vem com uma classe Controller.

* Em App você terá suas Models.

* Em Database/migrations você terá as suas Migrations. As Migrations servem para você criar a sua tabela do banco e fazer alterações. 

# 1º Passo – A model deverá ser criada primeiro, para criar uma model você deverá entrar na pasta de seu projeto pelo terminal, e lançar o seguinte comando: 
	php artisan make:model <nome da model> 
* Você pode criar a migration junto com a model, a vantagem disto é que as chances de não haver problemas depois são grandes. A model deverá ser criada sempre no Singular, por exemplo: 
	php artisan make:model Aluno

* Para criar a migration desta model é só adicionar o parâmetro –m
	php artisan make:model Aluno –m
* Assim, o laravel pegará o nome da sua model deixará ela com todas as letras minúsculas e adicionará um s, assim o nome da sua tabela ficaria alunos.

