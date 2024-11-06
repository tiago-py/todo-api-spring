
# Todo API

Esta é uma API REST para gerenciamento de tarefas (to-dos), construída com Spring Boot. A API fornece endpoints para criar, listar, buscar, atualizar e excluir tarefas.

## Endpoints

### 1. Criar Nova Tarefa

- **URL:** `/api/todos`
- **Método:** `POST`
- **Descrição:** Cria uma nova tarefa no sistema.
- **Corpo da Requisição:**
  ```json
  {
    "title": "Comprar mantimentos",
    "description": "Leite, pão, ovos",
    "completed": false
  }
  ```
- **Resposta de Sucesso:**
    - **Código:** `200 OK`
    - **Corpo:** Retorna o objeto da tarefa criada, incluindo o `id` gerado automaticamente.
  ```json
  {
    "id": 1,
    "title": "Comprar mantimentos",
    "description": "Leite, pão, ovos",
    "completed": false
  }
  ```

### 2. Listar Todas as Tarefas

- **URL:** `/api/todos`
- **Método:** `GET`
- **Descrição:** Retorna uma lista de todas as tarefas.
- **Resposta de Sucesso:**
    - **Código:** `200 OK`
    - **Corpo:** Uma lista de objetos de tarefa.
  ```json
  [
    {
      "id": 1,
      "title": "Comprar mantimentos",
      "description": "Leite, pão, ovos",
      "completed": false
    },
    {
      "id": 2,
      "title": "Limpar a casa",
      "description": "Aspirar e tirar o pó dos móveis",
      "completed": true
    }
  ]
  ```

### 3. Buscar Tarefa por ID

- **URL:** `/api/todos/{id}`
- **Método:** `GET`
- **Descrição:** Busca uma tarefa específica pelo `id`.
- **Parâmetro de URL:** `id` (Long) - ID da tarefa.
- **Resposta de Sucesso:**
    - **Código:** `200 OK`
    - **Corpo:** Objeto da tarefa correspondente.
  ```json
  {
    "id": 1,
    "title": "Comprar mantimentos",
    "description": "Leite, pão, ovos",
    "completed": false
  }
  ```
- **Erro:**
    - **Código:** `404 Not Found` - Se a tarefa não for encontrada.

### 4. Atualizar Tarefa

- **URL:** `/api/todos/{id}`
- **Método:** `PUT`
- **Descrição:** Atualiza uma tarefa existente.
- **Parâmetro de URL:** `id` (Long) - ID da tarefa.
- **Corpo da Requisição:**
  ```json
  {
    "title": "Comprar mantimentos",
    "description": "Leite, pão, ovos e frutas",
    "completed": false
  }
  ```
- **Resposta de Sucesso:**
    - **Código:** `200 OK`
    - **Corpo:** Retorna a tarefa atualizada.
  ```json
  {
    "id": 1,
    "title": "Comprar mantimentos",
    "description": "Leite, pão, ovos e frutas",
    "completed": false
  }
  ```
- **Erro:**
    - **Código:** `404 Not Found` - Se a tarefa não for encontrada.

### 5. Excluir Tarefa

- **URL:** `/api/todos/{id}`
- **Método:** `DELETE`
- **Descrição:** Exclui uma tarefa pelo `id`.
- **Parâmetro de URL:** `id` (Long) - ID da tarefa.
- **Resposta de Sucesso:**
    - **Código:** `204 No Content` - Se a exclusão foi bem-sucedida.
- **Erro:**
    - **Código:** `404 Not Found` - Se a tarefa não for encontrada.

## Configuração e Execução

Para executar este projeto, você precisa do [Java 11+](https://www.oracle.com/java/technologies/javase-downloads.html) e [Maven](https://maven.apache.org/) instalados.

### Passos para Execução

1. Clone o repositório:
   ```bash
   git clone https://github.com/seu_usuario/todo-api.git
   cd todo-api
   ```

2. Compile e execute o projeto:
   ```bash
   mvn spring-boot:run
   ```

3. A API estará disponível em `http://localhost:8080/api/todos`.

## Estrutura do Projeto

- **Controller**: `TodoController.java` - contém todos os endpoints REST para gerenciamento de tarefas.
- **Model**: `Todo.java` - representa a entidade `Todo`.
- **Repository**: `TodoRepository.java` - interface para operações CRUD.

## Tecnologias Utilizadas

- **Spring Boot** - Framework para desenvolvimento rápido de aplicações Java.
- **Spring Data JPA** - Abstração para operações com banco de dados.
- **H2 Database (ou outro banco)** - Banco de dados em memória para desenvolvimento rápido.

## Autor

Desenvolvido por **Tiago Braga e Gustavo Soares**.

---

**Observação:** Este é um projeto de exemplo para fins de aprendizado e não está otimizado para produção.
