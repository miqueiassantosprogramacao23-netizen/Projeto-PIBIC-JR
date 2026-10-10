## RELATÓRIO DE ATIVIDADES - OUTUBRO/2026
### Projeto: Assistente Conversacional para Avaliação Formativa em Lógica de Programação

**Atividade executada:** Mapeamento Estrutural das Categorias de Erros Lógicos e Sintáticos.

**Descrição:**
Durante o mês de outubro, foi realizado o levantamento empírico e a categorização dos erros mais frequentes cometidos por estudantes do primeiro ano nas disciplinas de Lógica de Programação e Introdução à Programação (C/C++). A metodologia baseou-se na observação direta e na revisão de erros comuns em sala de aula.

**Resultados obtidos:**
- Criação de um catálogo inicial com 9 tipologias de erros, divididas em:
  - **Erros Sintáticos (4):** Pontuação (ponto e vírgula), digitação de palavras reservadas, variáveis não declaradas e formatação de strings.
  - **Erros Lógicos (5):** Precedência matemática, inversão de condições, operadores relacionais incorretos (> vs >=), comparação de strings sensível a maiúsculas/minúsculas e confusão entre atribuição (=) e comparação (==).
- Estruturação das fichas com campos para: ID, Tipo, Categoria, Exemplo do aluno e Dica Socrática.

**Alinhamento com o projeto:**
Este mapeamento servirá como base de conhecimento para a parametrização do System Prompt da OpenAI API, permitindo que a IA classifique erros de forma autônoma e gere feedback heurístico sem fornecer respostas diretas, conforme previsto na metodologia do projeto.

**Próximos passos (Novembro):**
Início da estruturação das rotas de comunicação via Webhooks e configuração do ambiente de orquestração (Middleware/Make).
