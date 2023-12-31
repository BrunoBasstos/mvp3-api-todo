# ToDo API
![todo-app-diagrama](https://github.com/BrunoBasstos/mvp3-api-todo/assets/5402439/edf36b54-73c5-4994-a866-db021a6ac3b5)

Este é um MVP para conclusão da terceira sprint do curso de pós graduação em engenharia de software pela PUC-Rio.

A ToDo API é uma aplicação Flask que permite o gerenciamento de tarefas a serem realizadas, incluindo a adição, edição e
remoção de usuários, tarefas e prioridades. A API é protegida por autenticação de usuário e utiliza a biblioteca JWT
para geração de tokens de acesso.

Além disso, este projeto é composto por uma aplicação React que consome a API para fornecer uma interface amigável ao
usuário e uma outra api que intermedia a comunidação com a [OpenWeather API](http://openweathermap.org) para
obtenção de nomes de cidades e de previsão do tempo.

Os repositórios das aplicações podem ser encontrados em:
   - [ToDo-App](https://github.com/BrunoBasstos/mvp3-app-todo).
   - [Bridge Api](https://github.com/BrunoBasstos/mvp3-api-bridge)

## Rotas implementadas

- `GET /`: Redireciona para a tela de escolha do estilo de documentação.
- `GET /auth`: Retorna os dados do usuário autenticado.
- `GET /usuario`: Retorna uma lista de todos os usuários cadastrados na base de dados.
- `GET /usuario/<int:id>`: Retorna um usuário específico da base de dados.
- `POST /usuario`: Adiciona um novo usuário à base de dados.
- `PUT /usuario/<int:id>`: Atualiza um usuário específico da base de dados.
- `DELETE /usuario/<int:id>`: Deleta um usuário específico da base de dados.
- `GET /tarefa`: Retorna uma lista de todas as tarefas cadastradas na base de dados.
- `GET /tarefa/<int:id>`: Retorna uma tarefa específica da base de dados.
- `POST /tarefa`: Adiciona uma nova tarefa à base de dados.
- `PUT /tarefa/<int:id>`: Atualiza uma tarefa específica da base de dados.
- `DELETE /tarefa/<int:id>`: Deleta uma tarefa específica da base de dados.
- `GET /prioridade`: Retorna uma lista de todas as prioridades cadastradas na base de dados.
- `GET /status`: Retorna uma lista de todos os status cadastrados na base de dados.
- `POST /login`: Realiza a autenticação do usuário.

## Tecnologias utilizadas

- Flask
- Flask OpenAPI3
- Flask CORS
- Pydantic
- SQLAlchemy
- JWT
- Bcrypt
- SQLite
- Docker

## Pré-requisitos

Antes de executar o projeto, certifique-se de ter instalado:

- Python 3.6 ou superior: [https://www.python.org/downloads/](https://www.python.org/downloads/)
- pip (geralmente já incluído com
  Python): [https://pip.pypa.io/en/stable/installation/](https://pip.pypa.io/en/stable/installation/)
- Docker (caso deseje executar o projeto usando
  Docker): [https://docs.docker.com/get-docker/](https://docs.docker.com/get-docker/)

## Como executar

1. Clone o repositório.
2. Crie o arquivo .env usando o arquivo .env.example como base e configure seu ambiente. Recomendamos manter a aplicação rodando na porta 5000.
4. Crie e ative um ambiente virtual Python 3.
    1. No Windows, utilize o comando `python -m venv venv` para criar o ambiente virtual e `venv\Scripts\activate` para
       ativá-lo.
    2. No Linux, utilize o comando `python3 -m venv venv` para criar o ambiente virtual e `source venv/bin/activate`
       para ativá-lo.
5. Instale as dependências do projeto com o comando `pip install -r requirements.txt`.
6. Inicie a aplicação com o comando `python app.py`.
7. Acesse a documentação da API em `http://localhost:5000/openapi/swagger`.

## Como executar com Docker

1. Clone o repositório.
2. Crie o arquivo .env usando o arquivo .env.example como base e configure seu ambiente. Recomendamos manter a aplicação rodando na porta 5000.
3. Abrir o terminal na pasta do projeto.
4. Executar o comando `docker build -t todo-api .`.
5. Executar o comando `docker run --name todo-api -p 5000:5000 todo-api`.
    1. Note que isto criará um container com o nome todo-api. Para reiniciar a aplicação nas próximas vezes, basta
       executar o comando `docker start todo-api`. Caso você queira remover o container,
       execute `docker rm -f todo-api`.

> **IMPORTANTE** Não esqueça criar o arquivo .env da aplicação para que ela possa inicializar e se comunicar com as demais aplicações do projeto corretamente corretamente.

## Testes

Para executar os testes, basta executar o comando `pytest` na pasta raiz do projeto.

## Observações

Para facilitar o uso da API, foi criado um usuário administrador padrão com o email `admin@mail.com` e a
senha `admin1234`.

## Contribuições

Contribuições são sempre bem-vindas! Se você deseja contribuir com este projeto, por favor, abra uma issue para discutir
sua ideia antes de submeter um pull request.

## Licença

Este projeto está licenciado sob a licença MIT.

## TODO

- [ ] Aumentar cobertura de testes
- [ ] Implementar estratégias de paginação
- [ ] Separar a gerência de usuários em um microserviço
