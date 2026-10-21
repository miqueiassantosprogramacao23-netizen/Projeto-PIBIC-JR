# Catálogo de Erros - PIBIC Jr (Outubro)
## Foco: Mapeamento de Erros Sintáticos e Lógicos em Pseudocódigo/C

### ERRO-SINT-001 (Pontuação e Digitação)
* **Tipo:** Sintático
* **Onde ocorre:** C/C++ (Falta de ponto e vírgula, chaves, parênteses)
* **O que o aluno sente:** "O código está perfeito, por que não compila?"
* **Dica Socrática (IA):** "O compilador não entendeu onde sua instrução termina. Verifique se falta algum símbolo de pontuação no final da linha."

### ERRO-LOG-001 (Precedência Matemática)
* **Tipo:** Lógico
* **Onde ocorre:** Cálculos (Ex: Média)
* **O que o aluno fez:** `media = n1 + n2 / 2;`
* **Dica Socrática (IA):** "Lembre-se que na matemática a divisão vem antes da soma. Como podemos isolar a soma para que ela aconteça primeiro?"

### ERRO-LOG-002 (Inversão de Condicional)
* **Tipo:** Lógico
* **Onde ocorre:** Se/Senao (if-else)
* **O que o aluno fez:** Inverteu o feedback (Ex: Maior de idade recebe mensagem de menor).
* **Dica Socrática (IA):** "Observe a ordem das suas condições. Se a pessoa for maior de idade, o programa está respondendo o quê? A mensagem está no bloco correto?"

### ERRO-LOG-003 (Comparação Exata de Strings / Case Sensitivity)
* **Tipo:** Lógico
* **Onde ocorre:** Validação de textos (Ex: Pedir "sim" ou "não")
* **O que o aluno fez:** `se (resposta == "sim")` mas o usuário digitou "Sim" (com S maiúsculo). O programa diz que está errado.
* **Dica Socrática (IA):** "Os computadores são muito literais. Para a máquina, a letra 'S' maiúscula é igual à letra 's' minúscula? Como poderíamos padronizar o texto do usuário antes de comparar?"

### ERRO-SINT-002 (Inconsistência no Nome da Variável)
* **Tipo:** Sintático (mas o aluno acha que é lógico)
* **Onde ocorre:** Declaração e uso de variáveis de texto (Ex: `nomeAluno` vs `nome_aluno`)
* **O que o aluno fez:** Declarou `nomeAluno` mas na hora de imprimir escreveu `escreva(nome_aluno)`. O compilador trava dizendo "variável não declarada".
* **Dica Socrática (IA):** "O sistema diz que essa variável não existe. Vamos brincar de 'jogo dos 7 erros'? Compare exatamente como você escreveu o nome dela na linha 2 com a linha 5. Tem algum underline ou letra maiúscula sobrando?"

### ERRO-SINT-003 (Variável não declarada / Sem tipo)
* **Tipo:** Sintático
* **Onde ocorre:** Declaração de variáveis
* **O que o aluno fez:** Usou `idade = 18;` sem declarar `int idade;` antes, ou esqueceu o tipo da variável.
* **Dica Socrática (IA):** "O compilador diz que não conhece essa variável. Em C/C++, precisamos apresentar a variável ao computador antes de usá-la. Qual é o tipo de dado que 'idade' vai guardar? Onde você poderia declará-la?"

### ERRO-SINT-004 (String sem aspas ou aspas misturadas)
* **Tipo:** Sintático
* **Onde ocorre:** Uso de texto (strings)
* **O que o aluno fez:** `printf(Ola Mundo);` sem aspas, ou misturou `printf("Ola Mundo');` (abriu com aspas duplas e fechou com simples).
* **Dica Socrática (IA):** "Para o computador, um texto precisa estar 'embrulhado'. Verifique se você abriu e fechou as aspas do mesmo tipo. Está faltando algum símbolo de abertura ou fechamento?"

### ERRO-LOG-004 (Operador relacional incorreto: > vs >=)
* **Tipo:** Lógico
* **Onde ocorre:** Condições de maior/menor idade
* **O que o aluno fez:** Usou `idade > 18` quando deveria ser `idade >= 18`. Quem tem exatamente 18 anos recebe a mensagem errada.
* **Dica Socrática (IA):** "Pense na fronteira: se a pessoa tiver EXATAMENTE 18 anos, ela é maior ou menor? O operador que você escolheu inclui o número 18 ou apenas os números depois dele?"

### ERRO-LOG-005 (Atribuição vs Comparação: = vs ==)
* **Tipo:** Lógico (com sintaxe válida)
* **Onde ocorre:** Dentro de condições `if`
* **O que o aluno fez:** `if (idade = 18)` em vez de `if (idade == 18)`. O código compila, mas atribui 18 à variável e sempre retorna verdadeiro.
* **Dica Socrática (IA):** "Dentro do 'if', você quer VERIFICAR se a idade é 18 ou QUER MUDAR a idade para 18? O símbolo de um único igual faz uma dessas coisas, e o de dois iguais faz a outra. Qual você precisa aqui?"

### ERRO-SINT-005 (Confusão de Símbolos: Atribuição vs Comparação)
* **Tipo:** Sintático / Semântico (Mistura de linguagens)
* **Onde ocorre:** Transição do Pseudocódigo (Portugol) para C/Python.
* **O que o aluno fez:** No Portugol, usa-se `<-` para atribuir e `=` para comparar. No C, usa-se `=` para atribuir e `==` para comparar. O aluno escreve `if (idade = 18)` em C, achando que está comparando.
* **Dica Socrática (IA):** "Você está saindo do Portugol e indo para o C. Lembre-se que o símbolo que atribui um valor a uma variável é diferente do símbolo que verifica se dois valores são iguais. Qual deles você deve usar dentro do 'if' no C?"

### ERRO-LOG-006 (Loop Infinito no "Enquanto")
* **Tipo:** Lógico
* **Onde ocorre:** Estruturas de repetição (While/Enquanto)
* **O que o aluno fez:** Criou um loop `enquanto (x < 10)` mas esqueceu de colocar `x = x + 1` (ou `x++`) dentro do bloco. O programa trava rodando para sempre.
* **Dica Socrática (IA):** "O seu programa parece que parou de responder. Olhe para a condição do seu 'enquanto'. O que precisa acontecer com a variável 'x' a cada volta do loop para que essa condição deixe de ser verdadeira em algum momento?"

### ERRO-LOG-007 (Acesso a Índice Inválido em Vetores - "Index Out of Bounds")
* **Tipo:** Lógico (Erro de Memória/Execução)
* **Onde ocorre:** Manipulação de Arrays/Vetores
* **O que o aluno fez:** Declarou um vetor de 5 posições `int notas[5];` e tentou acessar `notas[5]`. (Em C/Python, os índices vão de 0 a 4).
* **Dica Socrática (IA):** "O sistema diz que você tentou acessar uma posição que não existe. Lembre-se que os computadores começam a contar do zero. Se o seu vetor tem tamanho 5, qual é o número do último índice válido?"
