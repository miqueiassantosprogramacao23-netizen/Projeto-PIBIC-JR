WebHook

é basicamente uma parte da arquitetura onde ele pega a informação enviada pelo o usuario, e manda para o outro sistema de forma automatica,
onde o outro sistema nao precise ficar perguntando o tempo todo.

1. O que é um Webhook?
Imagine que o sistema precisa avisar outro sistema que algo aconteceu.
Um Webhook é uma maneira de fazer essa comunicação acontecer automaticamente.
Pense em uma situação simples:
O aluno envia o código → o sistema recebe → o Webhook avisa outro sistema que existe uma nova informação para processar.

Aluno
  │
  │ envia código
  ▼
Webhook
  │
  │ envia os dados
  ▼
Outro sistema

O Webhook seria um dos pontos responsáveis por receber/encaminhar essa informação para o próximo componente da arquitetura.

Webhook é um mecanismo de comunicação em que, quando determinado evento acontece, os dados são enviados automaticamente para outro sistema, sem que esse outro sistema precise ficar perguntando repetidamente se há algo novo.

