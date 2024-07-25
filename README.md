# Flask Authentication Sample

Este projeto é uma aplicação Flask que implementa autenticação de usuários usando bcrypt e Flask-Login. Ele permite o registro de usuários, login, logout e operações CRUD em usuários.

## Índice

- [Introdução](#introdução)
- [Instalação](#instalação)
- [Uso](#uso)
- [Endpoints](#endpoints)
- [Contribuição](#contribuição)
- [Licença](#licença)

## Introdução

Esta aplicação Flask fornece funcionalidades de autenticação, incluindo login, logout, registro e operações CRUD para usuários. As senhas são protegidas com bcrypt.

## Instalação

### Requisitos

- Python 3.7+
- MySQL

### Passos de Instalação

1. Clone o repositório:
    ```sh
    git clone https://github.com/CaueGrassi7/sample-flask-auth.git
    ```
2. Navegue até o diretório do projeto:
    ```sh
    cd sample-flask-auth
    ```
3. Crie um ambiente virtual:
    ```sh
    python -m venv venv
    ```
4. Ative o ambiente virtual:
    - No Windows:
        ```sh
        venv\Scripts\activate
        ```
    - No macOS/Linux:
        ```sh
        source venv/bin/activate
        ```
5. Instale as dependências:
    ```sh
    pip install -r requirements.txt
    ```
6. Configure a string de conexão com o banco de dados MySQL no arquivo `app.py`:
    ```python
    app.config['SQLALCHEMY_DATABASE_URI'] = 'mysql+pymysql://usuario:senha@host:porta/nome_do_banco'
    ```
7. Execute a aplicação:
    ```sh
    python app.py
    ```

## Uso

A aplicação será executada em `http://127.0.0.1:5000/`.

### Endpoints

#### Registro de Usuário
- **URL:** `/user`
- **Método:** `POST`
- **Descrição:** Registra um novo usuário.
- **Dados da Requisição:**
    ```json
    {
        "username": "seu_usuario",
        "password": "sua_senha"
    }
    ```
- **Resposta de Sucesso:**
    ```json
    {
        "message": "User created"
    }
    ```

#### Login de Usuário
- **URL:** `/login`
- **Método:** `POST`
- **Descrição:** Autentica um usuário.
- **Dados da Requisição:**
    ```json
    {
        "username": "seu_usuario",
        "password": "sua_senha"
    }
    ```
- **Resposta de Sucesso:**
    ```json
    {
        "message": "Logged in"
    }
    ```

#### Logout de Usuário
- **URL:** `/logout`
- **Método:** `GET`
- **Descrição:** Encerra a sessão do usuário logado.
- **Resposta de Sucesso:**
    ```json
    {
        "message": "Logged out"
    }
    ```

#### Leitura de Usuário
- **URL:** `/user/<int:id_user>`
- **Método:** `GET`
- **Descrição:** Retorna os detalhes de um usuário.
- **Resposta de Sucesso:**
    ```json
    {
        "id": "id_do_usuario",
        "username": "nome_do_usuario"
    }
    ```

#### Atualização de Usuário
- **URL:** `/user/<int:id_user>`
- **Método:** `PUT`
- **Descrição:** Atualiza as informações de um usuário.
- **Dados da Requisição:**
    ```json
    {
        "password": "nova_senha"
    }
    ```
- **Resposta de Sucesso:**
    ```json
    {
        "message": "User id_user updated"
    }
    ```

#### Deleção de Usuário
- **URL:** `/user/<int:id_user>`
- **Método:** `DELETE`
- **Descrição:** Deleta um usuário.
- **Resposta de Sucesso:**
    ```json
    {
        "message": "User id_user deleted"
    }
    ```

## Contribuição

Contribuições são bem-vindas! Siga os passos abaixo para contribuir:

1. Faça um fork do projeto.
2. Crie uma branch para sua feature ou correção (`git checkout -b feature/nova-feature`).
3. Commit suas alterações (`git commit -am 'Adiciona nova feature'`).
4. Envie para a branch (`git push origin feature/nova-feature`).
5. Abra um Pull Request.

## Licença

Este projeto está licenciado sob a Licença MIT. Consulte o arquivo [LICENSE](LICENSE) para obter mais informações.
