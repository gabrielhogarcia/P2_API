# Atividade Final da Disciplina de Arquitetura de APIs

## Objetivo
Desenvolver uma API REST utilizando Spring Boot para gerenciar tarefas e colaboradores em uma equipe. A API permite operações CRUD (Create, Read, Update, Delete) para tarefas e colaboradores, com a possibilidade de vincular várias tarefas a diferentes colaboradores.

## Requisitos do Projeto

### 1. Modelo de Dados
Criação de duas entidades principais: **Tarefa** e **Colaborador**, com os seguintes atributos:

#### Tarefa
- `id` (Long): Identificador único da tarefa (gerado automaticamente).
- `titulo` (String): Título da tarefa. _(Obrigatório)_
- `descricao` (String): Descrição da tarefa.
- `dataCriacao` (LocalDate): Data de criação da tarefa. _(Obrigatório)_
- `dataInicio` (LocalDate): Data de início da tarefa.
- `dataConclusao` (LocalDate, opcional): Data de conclusão da tarefa.

#### Colaborador
- `id` (Long): Identificador único do colaborador (gerado automaticamente).
- `nome` (String): Nome do colaborador. _(Obrigatório)_

### 2. Relacionamentos
Configuração de um relacionamento muitos-para-muitos entre **Tarefa** e **Colaborador**:
- Uma tarefa pode ter vários colaboradores.
- Um colaborador pode estar vinculado a várias tarefas.

### 3. Repositórios
Criação de interfaces de repositório para as entidades **Tarefa** e **Colaborador** utilizando Spring Data JPA.

### 4. Serviços
Implementação de uma camada de serviço para encapsular a lógica de negócios, incluindo:
- Validação da existência de um colaborador ao associá-lo a uma tarefa.
- Atualização das informações da tarefa (como data de conclusão).

### 5. DTOs
Implementação de uma camada de transferência de dados (DTOs) para padronizar o envio e recebimento de dados entre cliente e servidor.

### 6. Endpoints da API
Implementação dos seguintes endpoints RESTful para operações CRUD:

#### Tarefas
- **POST** `/tarefas`: Cria uma nova tarefa e permite atribuir colaboradores a ela.
- **GET** `/tarefas`: Lista todas as tarefas.
- **GET** `/tarefas/{id}`: Obtém detalhes de uma tarefa específica, incluindo os colaboradores atribuídos.
- **PUT** `/tarefas/{id}`: Atualiza os dados de uma tarefa, incluindo colaboradores.
- **DELETE** `/tarefas/{id}`: Exclui uma tarefa.

#### Colaboradores
- **POST** `/colaboradores`: Cria um novo colaborador.
- **GET** `/colaboradores`: Lista todos os colaboradores.
- **GET** `/colaboradores/{id}`: Obtém detalhes de um colaborador específico, incluindo as tarefas atribuídas.
- **PUT** `/colaboradores/{id}`: Atualiza os dados de um colaborador.
- **DELETE** `/colaboradores/{id}`: Exclui um colaborador.

### 7. Tratamento de Erros
Adição de tratamento de exceções para erros comuns, como recurso não encontrado, requisições inválidas, e violação de integridade de dados.

### 8. Segurança (extra)
Implementação de uma camada de segurança utilizando Spring Security para proteger os endpoints da API.
