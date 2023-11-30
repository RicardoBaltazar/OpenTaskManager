# OpenHotelApp.api

## Descrição do Projeto

Este projeto é uma API Laravel voltada para reservas de quartos de hotéis. Criado como um projeto fictício para estudo e hobby, tem como objetivo adicionar progressivamente funcionalidades mais avançadas em cada versão. Planeja-se utilizar tecnologias como Docker, microserviços, mensageria, testes, explorar pesquisas avançadas com estruturas de dados e aprimorar a plataforma aos poucos.

## Documentação

A documentação da API e dos endpoints foi elaborada utilizando Swagger e pode ser acessada pelo endereço `base_url/api/documentation`.  
O endereço de `base_url` pode ser o localhost, caso o projeto esteja rodando locamente, ou a url base do projeto laravel rodando em produção.


## Funcionalidades

A seguir estão as principais funcionalidades do projeto:

1. **Login e Autenticação:** Os usuários podem fazer login e receber um token de autenticação para acessar os endpoints privados.
2. **Logout:** Os usuários podem efetuar logout, invalidando o token de autenticação. 

## Tecnologias Utilizadas

O projeto utiliza as seguintes tecnologias e práticas:

1. **Banco de Dados SQL:** O sistema utiliza um banco de dados SQL para armazenar informações.
2. **Testes Automatizados:** O projeto possui uma suíte de testes automatizados utilizando PHPUnit para garantir a estabilidade e a qualidade do código.
3. **Laravel:** O projeto é desenvolvido utilizando o framework Laravel.
4. **Laravel Sail:** O projeto tem o ambiente de desenvolvimento orquestrado pelo Laravel Sail
4. **Sanctum:** Para autenticação, o projeto faz uso do Sanctum.
5. **Telescope:** Utiliza o Telescope para facilitar a monitorização e registro de logs durante o desenvolvimento e depuração.
6. **Swagger:** A documentação da API é elaborada utilizando Swagger para oferecer uma visão detalhada dos endpoints disponíveis e suas funcionalidades.


## Requisitos

Antes de executar o projeto em seu ambiente de desenvolvimento, certifique-se de ter os seguintes requisitos atendidos:

- **WSL:** O projeto requer que você esteja usando Linux ou o WSL (Windows Subsystem for Linux) se estiver usando Windows.
- **Docker ou Docker Engine:** É necessário ter o Docker ou o Docker Engine instalado em seu ambiente. O Docker é uma plataforma que permite empacotar e distribuir aplicações em contêineres.

## Instalação e Configuração Local

Para instalar e configurar o projeto localmente, siga as etapas abaixo:

1. Clone este repositório em sua máquina local.

2. Certifique-se de que o Docker está em execução no seu ambiente de desenvolvimento.

3. Execute o seguinte comando no terminal para instalar as dependências do projeto:
     ```bash
     docker run --rm \
         -u "$(id -u):$(id -g)" \
         -v "$(pwd):/var/www/html" \
         -w /var/www/html \
         laravelsail/php82-composer:latest \
         composer install --ignore-platform-reqs
     ```
     Para mais informações, consulte a [documentação do Laravel Sail](link_laravel_sail).

4. Crie o arquivo `.env` e configure suas variáveis de ambiente com o seguinte comando no terminal:
     ```bash
     cp .env.example .env
     ```  
5. Para iniciar o ambiente de desenvolvimento, execute o comando no terminal:
     ```bash
     ./vendor/bin/sail up
     ```  

6. Após iniciar o laravel sail, execute o comando para criar uma chave de criptografia e adicioná-la ao seu arquivo .env:
    ```    
    ./vendor/bin/sail artisan key:generate
    ```

7. No terminal, após criar seu banco de dados com base nas suas variaveis de ambiente configuradas, execute para realizar as migrações do banco de dados:
     ```bash
     ./vendor/bin/sail artisan migrate
     ```

8. Se desejar preencher o banco de dados com dados fictícios, execute o seguinte comando no terminal:
     ```bash
     ./vendor/bin/sail artisan db:seed
     ```

9. Para encerrar o ambiente de desenvolvimento, execute no terminal:
     ```bash
     ./vendor/bin/sail down
     ```  

<!-- ## Recursos Externos

Durante o desenvolvimento do projeto XYZ, foram utilizados os seguintes recursos externos:

- [Biblioteca X](https://exemplo.com/biblioteca-x): Descrição da biblioteca X.
- [API de Pagamento Y](https://exemplo.com/api-pagamento-y): Integração com a API de pagamento Y para processar transações financeiras.
- [Framework Z](https://exemplo.com/framework-z): Utilização do framework Z para agilizar o desenvolvimento. -->

<!-- ## Licença

O projeto XYZ é licenciado sob a Licença MIT. Consulte o arquivo [LICENSE](https://github.com/seu-usuario/projeto-xyz/blob/main/LICENSE) para obter mais informações.    -->
