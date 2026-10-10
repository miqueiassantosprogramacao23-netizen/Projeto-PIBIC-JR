Orquestração de APIs

A orquestração é a forma de como o sistema vai funcionar, é um processo organizado por etapas, onde a proxima etapa precisa da primeira

Orquestração de APIs é a coordenação do fluxo de dados e das chamadas entre diferentes sistemas e serviços para realizar um processo completo.

Receber ingredientes
       ↓
Preparar
       ↓
Cozinhar
       ↓
Montar
       ↓
Servir


Receber código do aluno
       ↓
Interpretar os dados
       ↓
Enviar para a IA
       ↓
Receber resposta
       ↓
Separar os resultados
       ↓
Salvar na planilha



Imagine que Maria envie:
{
    "linguagem": "Python",
    "codigo": "idade = 17"
}

O sistema precisa coordenar várias coisas:
Etapa 1 — Receber
O Webhook recebe os dados.
↓
Etapa 2 — Processar
O middleware/orquestrador pega esses dados e prepara a requisição.
↓
Etapa 3 — Enviar
Os dados são enviados para a OpenAI API.
↓
Etapa 4 — Receber
A IA retorna a análise.
↓
Etapa 5 — Organizar
O sistema precisa interpretar a resposta JSON.
↓
Etapa 6 — Registrar
As informações de erro podem ser armazenadas na planilha.


Orquestrar = coordenar as diferentes etapas e sistemas de um processo para que os dados passem pelo fluxo necessário na ordem adequada.
