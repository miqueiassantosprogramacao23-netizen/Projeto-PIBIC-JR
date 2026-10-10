# JSON — JavaScript Object Notation

## O que é JSON?

JSON (JavaScript Object Notation) é um formato de texto utilizado para representar e transportar dados estruturados. Ele é independente de linguagem de programação e é amplamente utilizado na comunicação entre sistemas.

## Principais características

Um documento JSON pode representar:

- objetos;
- arrays;
- strings;
- números;
- valores booleanos (`true` e `false`);
- `null`.

Os objetos JSON utilizam pares de chave e valor.

Exemplo:

```json
{
  "nome": "João",
  "idade": 17,
  "curso": "Informática"
}
```

## Relação com o projeto PIBIC Jr.

No projeto, o JSON será utilizado para estruturar os dados que circulam entre os componentes do sistema, como a interface, os Webhooks, o middleware e a API de Inteligência Artificial.

O projeto prevê que a Inteligência Artificial produza dois objetos JSON: um contendo o feedback metodológico destinado ao estudante e outro contendo a classificação técnica do erro para posterior registro e análise.

### Como o JSON será utilizado no projeto

No projeto, o JSON será utilizado para organizar os dados durante a comunicação entre os diferentes componentes da arquitetura. O fluxo previsto inclui a interface de submissão do estudante, o Webhook, o middleware/orquestrador, a API de Inteligência Artificial e a planilha eletrônica.

A proposta também estabelece que a Inteligência Artificial deverá retornar dois objetos JSON distintos: um contendo a dica metodológica destinada ao estudante e outro contendo a classificação técnica do erro para o sistema.

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

Dessa forma, o JSON será importante para estruturar e transportar as informações utilizadas pelo sistema durante a integração entre seus componentes.

## Fontes consultadas

- IETF. RFC 8259 — The JavaScript Object Notation (JSON) Data Interchange Format.
- MDN Web Docs. Trabalhando com JSON.
