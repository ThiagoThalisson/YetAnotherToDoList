<div align="center">

# 📋 `YetAnotherToDoList` <!-- omit in toc -->

</div>

YetAnotherToDoList é uma aplicação simples de lista de tarefas desenvolvida com Spring Boot, permitindo aos usuários gerenciar tarefas e controlá-las com funcionalidades básicas, como a criação, listagem e atualização de tarefas.

- [🚗 `Recursos`](#-recursos)
- [📋 `Dependências`](#-dependências)
- [📥 `Instalação`](#-instalação)
  - [1.  Clonar O Repositório](#1--clonar-o-repositório)
  - [2.  Instalar As Dependências](#2--instalar-as-dependências)
  - [3.  Iniciar A Aplicação](#3--iniciar-a-aplicação)
- [⚙️ `Uso`](#️-uso)
  - [Criação Do Usuário](#criação-do-usuário)
  - [Criar Uma Tarefa](#criar-uma-tarefa)
  - [Listar Tarefas](#listar-tarefas)
  - [Atualizar Uma tarefa](#atualizar-uma-tarefa)
- [📺 `Desenvolvimento Local`](#-desenvolvimento-local)
  - [Habilitar Reload Automático](#habilitar-reload-automático)
  - [Comando Para Rodar A Aplicação Localmente](#comando-para-rodar-a-aplicação-localmente)

## 🚗 `Recursos`

* Criação de tarefas.
* Listagem de tarefas.
* Atualização de tarefas.
* Validação de título de tarefas com limite de caracteres.
* Validação de data de início e término.

## 📋 `Dependências`

* Java 17
* Spring Boot
* Maven
* Spring Boot DevTools (para reinicialização automática durante o desenvolvimento)

## 📥 `Instalação`

Para rodar a aplicação localmente, siga os seguintes passos:

### 1.  Clonar O Repositório

```bash
git clone https://github.com/ThiagoThalisson/YetAnotherToDoList.git
cd yetanothertodolist
```

### 2.  Instalar As Dependências

Se você ainda não tiver o Maven instalado, instale o Maven antes de continuar.

Instale as dependências com o comando:

```bash
mvn clean install
```

### 3.  Iniciar A Aplicação

Para rodar a aplicação localmente, use o seguinte comando:

```bash
mvn spring-boot:run
```

A aplicação estará disponível em `http://localhost:8080`.

## ⚙️ `Uso`

Após iniciar a aplicação, você pode interagir com a API para realizar as operações:

### Criação Do Usuário
Crie um usuário com uma requisição POST para `/users/`.
```json
{
    "name": "Thiago",
    "username": "thiagot",
    "password": "123"
}
```


### Criar Uma Tarefa

Envia uma requisição POST para `/tasks/` com o corpo contendo os detalhes da tarefa:

```json
{
  "title": "Estudar Spring Boot",
  "description": "Revisar conceitos e aprender novas funcionalidades",
  "startAt": "2025-03-05T09:00:00",
  "endAt": "2025-03-05T18:00:00"
}
```
A maioria das rotas é protegida por autenticação básica HTTP. Para usar a autenticação básica HTTP, você precisa incluir um cabeçalho de autorização com cada solicitação. Por exemplo:

Authorization: Basic <credenciais>

Substitua <credenciais> por um conjunto de nome de usuário e senha com codificação Base64. Por exemplo, se o nome de usuário for admin e a senha for senha123, você deverá usar o seguinte cabeçalho:

Authorization: Basic YWRtaW46c2VuaGExMjM=

Você pode usar um codificador Base64 online para gerar o valor correto para o cabeçalho de autorização.

### Listar Tarefas

Envia uma requisição GET para `/tasks/` para listar todas as tarefas criadas.

### Atualizar Uma tarefa

Envia uma requisição PUT para `/tasks/{id}` para atualizar uma tarefa existente, passando o ID da tarefa na URL e os novos dados no corpo da requisição.

## 📺 `Desenvolvimento Local`

### Habilitar Reload Automático

Adicione o `spring-boot-devtools` no `pom.xml` para reinicialização automática durante o desenvolvimento:

```xml
<dependencies>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-devtools</artifactId>
        <optional>true</optional>
    </dependency>
</dependencies>
```

### Comando Para Rodar A Aplicação Localmente

Após realizar modificações, você pode iniciar o projeto com o comando:

```bash
mvn spring-boot:run
```

[⬆ Back To Top]()