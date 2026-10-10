
# Resumo de Setembro — Revisão da Literatura Técnica

## 1. Visão geral

Durante o mês de setembro, foram estudados conceitos relacionados à comunicação e integração entre sistemas, estruturação de dados e avaliação formativa. Esses conceitos fazem parte da base técnica do projeto de pesquisa **“Assistente Conversacional para Avaliação Formativa e Correção Automatizada em Lógica de Programação: Integração de APIs e Inteligência Artificial Generativa”**.

Os principais conceitos estudados foram:

- **JSON** → formato utilizado para representar e transportar dados estruturados.
- **API** → interface que permite a comunicação entre sistemas ou aplicações.
- **HTTP** → protocolo utilizado para comunicação na Web.
- **REST** → estilo arquitetural para sistemas distribuídos, utilizado como base para muitos serviços Web.
- **Webhook** → mecanismo que permite enviar dados automaticamente quando determinado evento ocorre.
- **Orquestração de APIs** → coordenação do fluxo de dados e das chamadas entre diferentes sistemas e serviços.
- **Avaliação formativa** → processo de avaliação que utiliza evidências sobre a aprendizagem para fornecer feedback e orientar melhorias.

---

# 2. JSON — JavaScript Object Notation

## 2.1 O que é JSON?

JSON (JavaScript Object Notation) é um formato de texto utilizado para representar e transportar dados estruturados. É independente de linguagem de programação e é amplamente utilizado na troca de dados entre aplicações.

O JSON pode representar diferentes tipos de valores, incluindo:

- objetos;
- arrays;
- strings;
- números;
- valores booleanos (`true` e `false`);
- `null`.

Os objetos JSON utilizam pares de **chave e valor**.

Exemplo:

```json
{
    "nome": "João",
    "idade": 17,
    "curso": "Informática"
}
```

O padrão JSON é especificado pela RFC 8259 da IETF. A documentação da MDN também apresenta o JSON como um formato baseado em texto utilizado para representar dados estruturados e transmitir informações em aplicações Web.

## 2.2 Relação com o projeto PIBIC Jr.

No projeto, o JSON será utilizado para estruturar os dados que circulam entre os componentes do sistema, como a interface do estudante, os Webhooks, o middleware/orquestrador, a API de Inteligência Artificial e a planilha eletrônica.

O projeto prevê também que a Inteligência Artificial produza dois objetos JSON distintos: um contendo o feedback metodológico destinado ao estudante e outro contendo a classificação técnica do erro para posterior registro e análise.

Exemplo simplificado de dados enviados ao sistema:

```json
{
    "aluno": {
        "nome": "Maria",
        "linguagem": "Python",
        "codigo": "idade = 17"
    }
}
```

Dessa forma, o JSON será importante para estruturar e transportar as informações utilizadas durante a integração entre os componentes do sistema.

### Fontes

- IETF. **RFC 8259 — The JavaScript Object Notation (JSON) Data Interchange Format**.
- MDN Web Docs. **Trabalhando com JSON**.

---

# 3. API — Application Programming Interface

## 3.1 O que é uma API?

API (Application Programming Interface) é uma interface que define uma forma de comunicação entre diferentes sistemas ou aplicações, permitindo o acesso a dados ou funcionalidades de maneira organizada e padronizada.

Uma analogia utilizada durante o estudo foi a de um **mensageiro**.

Por exemplo, imagine uma plataforma de filmes. Em vez de cadastrar manualmente todos os filmes existentes, a plataforma poderia utilizar uma API de outro serviço que disponibilize essas informações.

O funcionamento simplificado seria:

```text
Meu sistema
     │
     │ solicitação
     ▼
    API
     │
     │ comunicação
     ▼
Outro sistema
     │
     │ resposta
     ▼
    API
     │
     ▼
Meu sistema
```

Portanto, uma API funciona como uma interface que permite que sistemas diferentes realizem uma comunicação estruturada.

## 3.2 Relação com o projeto

No projeto PIBIC Jr., uma das APIs utilizadas será a API de Inteligência Artificial, que receberá informações relacionadas ao código do estudante e retornará uma análise.

O projeto descreve a utilização da API de Inteligência Artificial como parte do núcleo cognitivo do sistema.

### Fonte

- Projeto de Pesquisa IC Jr. 2026–2027 — IFAM, especialmente a descrição da arquitetura e dos objetivos do projeto.

---

# 4. HTTP — Hypertext Transfer Protocol

## 4.1 O que é HTTP?

HTTP (Hypertext Transfer Protocol) é um protocolo de comunicação utilizado na Web. Ele segue um modelo de requisição e resposta entre cliente e servidor.

De forma simplificada:

```text
Cliente
   │
   │ requisição HTTP
   ▼
Servidor
   │
   │ resposta HTTP
   ▼
Cliente
```

As mensagens HTTP são divididas principalmente em **requisições** e **respostas**.

Uma requisição pode indicar, por exemplo, que o cliente deseja consultar ou enviar determinada informação.

## 4.2 Métodos HTTP

O HTTP possui diferentes métodos de requisição. Entre eles estão:

- `GET`
- `POST`
- `PUT`
- `DELETE`
- `PATCH`

No projeto, os métodos `GET` e `POST` são especialmente importantes.

### GET

O método `GET` é utilizado para solicitar ou consultar uma representação de um recurso.

Exemplo:

```text
GET /avaliacoes/25
```

Pode ser interpretado como:

> "Quero consultar a avaliação número 25."

### POST

O método `POST` é utilizado para enviar dados a um recurso ou processo do servidor.

Exemplo:

```text
POST /avaliacoes
```

Com dados como:

```json
{
    "linguagem": "Python",
    "codigo": "idade = 17"
}
```

No contexto do projeto, o `POST` pode ser utilizado para enviar os dados do código do estudante para processamento e análise.

Portanto:

```text
GET  → solicitar/consultar dados

POST → enviar dados para processamento ou criação de algo
```

### Fonte

- MDN Web Docs. **Uma visão geral do HTTP**.
- MDN Web Docs. **Métodos de requisição HTTP**.

---

# 5. REST — Representational State Transfer

## 5.1 O que é REST?

REST significa **Representational State Transfer**.

REST não é um protocolo como HTTP. É um **estilo arquitetural** para sistemas distribuídos, definido por Roy Fielding em sua tese de doutorado de 2000.

REST estabelece restrições arquiteturais que buscam, entre outros aspectos, favorecer a escalabilidade das interações, interfaces gerais e a independência entre componentes.

Uma representação simplificada é:

```text
Cliente
   │
   │ HTTP
   ▼
API REST
   │
   ▼
Recurso
```

Em uma API que segue princípios RESTful, os recursos são identificados e as operações são realizadas por meio dos mecanismos definidos pelo protocolo utilizado, frequentemente HTTP.

Exemplo:

```text
GET    /avaliacoes
GET    /avaliacoes/25
POST   /avaliacoes
PUT    /avaliacoes/25
DELETE /avaliacoes/25
```

É importante entender que `GET`, `POST`, `PUT` e `DELETE` são **métodos HTTP**. Eles não são "métodos REST". O REST utiliza as capacidades do HTTP dentro de uma arquitetura que segue suas restrições.

## 5.2 Relação entre os conceitos

Uma forma simplificada de relacionar os conceitos estudados é:

```text
JSON
  ↓
representação dos dados

HTTP
  ↓
protocolo de comunicação

REST
  ↓
estilo arquitetural

API
  ↓
interface de comunicação
```

O projeto menciona explicitamente a utilização de **requisições HTTP RESTful** e utiliza como referência a obra *RESTful Web Services*, de Leonard Richardson e Sam Ruby.

### Fontes

- Fielding, Roy T. **Architectural Styles and the Design of Network-based Software Architectures**. University of California, Irvine, 2000.
- Richardson, Leonard; Ruby, Sam. **RESTful Web Services**. O'Reilly Media, 2007.

---

# 6. Webhook

## 6.1 O que é um Webhook?

Um Webhook é um mecanismo de comunicação baseado em eventos. Quando determinado evento ocorre, um sistema pode enviar automaticamente uma requisição HTTP para uma URL previamente configurada.

Dessa forma, o sistema que recebe a informação não precisa ficar perguntando repetidamente se algo novo aconteceu.

Uma representação simplificada:

```text
Evento acontece
      ↓
Webhook é acionado
      ↓
Requisição HTTP
      ↓
Sistema receptor
```

Uma diferença importante é:

```text
Polling:

Sistema → "Aconteceu algo?"
Sistema → "Aconteceu algo?"
Sistema → "Aconteceu algo?"
Sistema → "Aconteceu algo?"

Webhook:

Evento acontece
      ↓
Sistema é avisado automaticamente
```

## 6.2 Relação com o projeto

No projeto PIBIC Jr., os Webhooks fazem parte da arquitetura de integração:

```text
Interface
    ↓
Webhook
    ↓
Middleware / Orquestrador
    ↓
OpenAI API
    ↓
Planilha
```

O projeto prevê a criação de rotas de Webhook e a utilização de JSON e de nós de orquestração para realizar a integração entre os componentes.

É importante destacar que, no projeto, o Webhook será implementado de acordo com a arquitetura definida posteriormente. Portanto, neste momento, o estudo estabelece o conceito geral de Webhook, mas não define sozinho todos os detalhes da implementação.

### Fonte

- GitHub Docs. **About webhooks** — documentação sobre Webhooks e comunicação orientada a eventos.

---

# 7. Orquestração de APIs

## 7.1 O que significa orquestrar?

Orquestrar significa **coordenar diferentes etapas, componentes e serviços para que um processo completo seja executado de maneira organizada**.

Uma analogia utilizada durante o estudo foi uma receita:

```text
Receber ingredientes
       ↓
Preparar
       ↓
Cozinhar
       ↓
Montar
       ↓
Servir
```

Cada etapa faz parte do processo.

No sistema do projeto, podemos representar uma sequência semelhante:

```text
Receber código do aluno
       ↓
Interpretar os dados
       ↓
Enviar para a IA
       ↓
Receber resposta
       ↓
Interpretar a resposta
       ↓
Registrar os resultados
```

## 7.2 Aplicação no projeto

Imagine que Maria envie:

```json
{
    "linguagem": "Python",
    "codigo": "idade = 17"
}
```

O fluxo previsto pode ser compreendido de maneira simplificada:

```text
1. Webhook recebe os dados
          ↓
2. Middleware/orquestrador processa os dados
          ↓
3. Dados são enviados para a OpenAI API
          ↓
4. IA retorna a análise
          ↓
5. Sistema interpreta a resposta JSON
          ↓
6. Informações de erro são registradas
```

O projeto estabelece justamente uma arquitetura envolvendo **Interface → Webhook → Middleware/Make → OpenAI API → Spreadsheet** e prevê o processamento da resposta da IA para registro das classificações dos erros. 

Portanto:

> **Orquestrar é coordenar as diferentes etapas e sistemas de um processo para que os dados sigam o fluxo necessário até a conclusão da tarefa.**

### Fonte

- Projeto de Pesquisa IC Jr. 2026–2027 — IFAM, seção de metodologia e arquitetura do sistema.

---

# 8. Avaliação Formativa

## 8.1 O que é avaliação formativa?

A avaliação formativa está relacionada ao uso de informações obtidas durante o processo de aprendizagem para fornecer **feedback que possa ser utilizado para melhorar o ensino e a aprendizagem**.

Black e Wiliam, em sua revisão da literatura sobre avaliação formativa, discutem a importância do feedback frequente e do uso das informações obtidas na avaliação para orientar o processo de aprendizagem.

Portanto, a avaliação formativa não consiste simplesmente em informar:

```text
"Está errado."
```

Ela procura fornecer informações que ajudem o estudante a compreender sua situação e identificar caminhos para melhorar.

## 8.2 Aplicação no projeto

No projeto PIBIC Jr., a Inteligência Artificial será utilizada como um assistente para fornecer feedback ao estudante durante a aprendizagem de lógica de programação.

Por exemplo, diante de um erro lógico, em vez de entregar diretamente o código corrigido:

```text
❌ Seu código está errado.
A resposta correta é:
[código completo]
```

o sistema deverá fornecer uma orientação:

```text
Existe um problema na condição utilizada.

Analise o que acontece quando o valor
é igual a 10 e verifique se a condição
produz o comportamento esperado.
```

Nesse caso, o estudante recebe uma **pista**, mas precisa participar do processo de raciocínio para encontrar e corrigir o erro.

Essa proposta está relacionada ao objetivo do projeto de desenvolver e calibrar um mecanismo de **Prompt Engineering com comportamento de tutor socrático**, evitando que a IA forneça diretamente a solução completa.

## 8.3 Duas funções da IA no projeto

O projeto prevê dois tipos de resultado:

```text
             IA
              │
       ┌──────┴──────┐
       ▼             ▼
   Feedback       Classificação
  ao estudante      do erro
       │             │
       ▼             ▼
    Aprendizagem   Registro/
                  análise
```

O primeiro resultado possui finalidade pedagógica: ajudar o estudante a raciocinar sobre seu erro.

O segundo possui finalidade técnica e de pesquisa: classificar os erros para que eles possam ser registrados, contabilizados e posteriormente analisados.

### Fonte principal

- Black, Paul; Wiliam, Dylan. **Assessment and Classroom Learning**. *Assessment in Education: Principles, Policy & Practice*, v. 5, n. 1, p. 7–74, 1998. DOI: 10.1080/0969595980050102.

### Referência relacionada

- Black, Paul; Wiliam, Dylan. **Inside the Black Box: Raising Standards Through Classroom Assessment**. *Phi Delta Kappan*, 1998.

---

# 9. Integração dos conceitos no projeto

Depois do estudo realizado em setembro, os conceitos podem ser relacionados da seguinte forma:

```text
                         ALUNO
                           │
                           │
                           │ JSON
                           ▼
                       WEBHOOK
                           │
                           │ HTTP
                           ▼
                 MIDDLEWARE / ORQUESTRADOR
                           │
                           │ HTTP / REST
                           ▼
                     OPENAI API
                           │
                    ┌──────┴──────┐
                    ▼             ▼
               FEEDBACK       CLASSIFICAÇÃO
              AO ALUNO          DO ERRO
                    │             │
                    ▼             ▼
               APRENDIZAGEM    PLANILHA
```

Cada conceito possui uma função diferente:

| Conceito | Função no projeto |
|---|---|
| JSON | Estruturar e transportar os dados |
| API | Permitir a comunicação entre sistemas |
| HTTP | Realizar a comunicação por meio de requisições e respostas |
| REST | Fornecer um estilo arquitetural para organização de serviços Web |
| Webhook | Disparar/entregar dados quando um evento ocorre |
| Orquestração | Coordenar o fluxo entre os diferentes componentes |
| OpenAI API | Realizar a análise utilizando Inteligência Artificial |
| Avaliação formativa | Orientar o aprendizado por meio do feedback |
| Planilha | Registrar e organizar as classificações dos erros |

Essa integração corresponde à arquitetura e aos objetivos descritos no projeto de pesquisa.

---

# 10. Referências utilizadas

**BLACK, Paul; WILIAM, Dylan.** Assessment and Classroom Learning. *Assessment in Education: Principles, Policy & Practice*, v. 5, n. 1, p. 7–74, 1998. DOI: 10.1080/0969595980050102.

**FIELDING, Roy Thomas.** *Architectural Styles and the Design of Network-based Software Architectures*. Doctoral dissertation. University of California, Irvine, 2000.

**IETF.** *RFC 8259: The JavaScript Object Notation (JSON) Data Interchange Format*. 2017.

**RICHARDSON, Leonard; RUBY, Sam.** *RESTful Web Services*. O'Reilly Media, 2007.

**MDN WEB DOCS.** *Trabalhando com JSON*.

**MDN WEB DOCS.** *Uma visão geral do HTTP*.

**MDN WEB DOCS.** *Métodos de requisição HTTP*.

**GITHUB DOCS.** *About webhooks*.

**IFAM.** *Projeto de Pesquisa IC Jr. 2026–2027: Assistente Conversacional para Avaliação Formativa e Correção Automatizada em Lógica de Programação: Integração de APIs e Inteligência Artificial Generativa*. 2026.
