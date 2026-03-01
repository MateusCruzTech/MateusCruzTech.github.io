---
layout: projeto 
title: API REST de Cidades Brasileiras
tagline: API RESTful em Java/Spring Boot para consulta e análise de dados de cidades brasileiras.
link: https://github.com/MateusCruzTech/API_Rest_Brazilian_Cities 
image: /assets/image/image.png 
---
<link rel="stylesheet" href="{{ '/assets/css/project.css' | relative_url }}"> 


#  API REST de Cidades Brasileiras (Portfólio Backend)

## Visão Geral do Projeto
### Visão Geral da Documentação

![Visão geral dos endpoints da API no Swagger UI](/assets/image/Swagger-api-rest-brazil-cities.png)

Este projeto é uma API RESTful desenvolvida em **Java** com **Spring Boot** que expõe dados detalhados de cidades brasileiras, creditos ao dataset: [Link datase](https://www.kaggle.com/datasets/crisparada/brazilian-cities).
O principal objetivo é demonstrar habilidades de Backend, focando em:

1.  **Parsing Robusto:** Leitura de dados não-estruturados (CSV) com tratamento de erros (`NumberFormatException`) para valores nulos/ausentes.
2.  **Arquitetura em Camadas:** Implementação das camadas Model, Service (`@PostConstruct`) e Controller.
3.  **Documentação Profissional:** Integração com **Swagger/OpenAPI** para facilitar o teste e o uso da API.

### Funcionalidade Principal

A API carrega e armazena mais de 5.500 registros de cidades (incluindo População, IDH, Coordenadas Geográficas e PIB) a partir do arquivo `BRAZIL_CITIES.csv`, disponibilizando-os para consulta via endpoints HTTP.

---

## Tecnologias Utilizadas

| Categoria | Tecnologia | Versão |
| :--- | :--- |:-------|
| **Linguagem** | Java | 17+ |
| **Framework** | Spring Boot | 3.5.6 |
| **Parsing de Dados**| OpenCSV | Latest |
| **Facilitador** | Lombok | Latest |
| **Documentação** | Springdoc OpenAPI (Swagger UI) | 

## Estrutura em Camadas

A aplicação é estruturada para escalabilidade e manutenibilidade:

* **`City.java` (Model):** Define a estrutura dos dados, com o uso de Lombok e tipos corretos (`Double` para coordenadas e índices).
* **`CityService.java` (Service):** Contém a lógica de *parsing* e carregamento de dados. O método `@PostConstruct` garante que os dados sejam carregados **apenas uma vez** na inicialização da aplicação.
* **`CityController.java` (Controller):** Expõe os endpoints REST e usa Injeção de Dependência (`@Autowired`) para acessar o Service.

## Como Executar o Projeto Localmente

### Pré-requisitos

* Java Development Kit (JDK) 17 ou superior.
* Maven ou Gradle.

### Passos de Execução (Maven)

1.  **Clone o Repositório:**
    ```bash
    git clone [https://github.com/MateusCruzTech/API_Rest_Brazilian_Cities](https://github.com/MateusCruzTech/API_Rest_Brazilian_Cities)
    cd API_Rest_Brazilian_Cities
    ```

2.  **Construa e Execute:**
    ```bash
    # Constrói o projeto e baixa dependências
    mvn clean install 
    
    # Executa a aplicação Spring Boot
    mvn spring-boot:run
    ```
    *A aplicação será iniciada na porta 8080*

## Documentação e Testes (Swagger UI)

Após a aplicação ser iniciada, a documentação interativa da API está disponível no seu navegador:

### **URL do Swagger UI:**
 **`http://localhost:8080/swagger-ui.html`**

### Endpoints Principais

| Método | Endpoint | Descrição | 
| :--- |:--- |:--- | 
| `GET` | `/api/city` | Retorna a lista completa de todas as cidades carregadas em memória. | 
| `GET` | `/api//hdi/{symbol}/{valueParameter}` | Busca todas as cidade de acordo com uma condição especificada e um valor a ser comparado com hdi | 
| `GET` | `/api/hdiScore/{symbol}/{valueParameter}` | Busca e classifica todas as cidade de acordo com uma condição especificada e um valor a ser comparado com o rank do hdi |
| `GET` | `/isCapital/{valueParameter}` | Buscas as cidades de acordo com parâmetro true ou false para Capital | 

---

### **Demonstração:**
#### Get de todas as cidades
![Visão geral dos endpoints da API no Swagger UI](/assets/image/imgGet.png)

#### Get das cidades que são capitais
![Visão geral dos endpoints da API no Swagger UI](/assets/image/imgGet2.png)

#### Get das cidades que possuem um hdi maior que 0.8
![Visão geral dos endpoints da API no Swagger UI](/assets/image/imgGet3.png)

#### Get das cidades que estão em um rank menor que 100
![Visão geral dos endpoints da API no Swagger UI](/assets/image/imgGet4.png)


## Contato

Conecte-se comigo:

* LinkedIn: [Link](https://www.linkedin.com/in/mateus-henrique-172599236/)