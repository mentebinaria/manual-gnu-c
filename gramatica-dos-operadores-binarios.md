---
layout:
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# 🐫 Gramática dos Operadores Binários

Operadores binários são aqueles que recebem dois operandos, um à esquerda e outro à direita.

Todos os operadores binários em C são sintaticamente associativos à esquerda. Isso significa que `a op b op c` significa `(a op b) op c`. No entanto, os únicos operadores que você deve repetir dessa forma sem parênteses são `+`, `-`, `*` e `/`, pois esses casos são claros na álgebra. Então, é aceitável escrever `a + b + c` ou `a - b - c`, mas nunca `a == b == c` ou `a % b % c`. Para esses operadores, use parênteses explícitos para mostrar como as operações se aninham.

Cada operador em C possui uma precedência, que é sua posição na ordem gramatical entre os vários operadores. Os operadores com a maior precedência capturam operandos adjacentes primeiro; essas expressões, então, se tornam operandos para operadores de menor precedência.

A ordem de precedência dos operadores em C é totalmente especificada, portanto, qualquer combinação de operações leva a um aninhamento bem definido. Declaramos apenas uma parte da ordem completa de precedência aqui, pois é uma má prática para o código C depender dos outros casos. Para casos não especificados neste capítulo, sempre use parênteses para tornar o aninhamento explícito.

Você pode depender desta subsequência da ordem de precedência (de maior para menor):

* Operações pós-fixadas: acesso a um campo ou alternativa (‘.’ e ‘->’), indexação de array, chamadas de função e operadores unários pós-fixados.
* Operadores unários prefixados.
* Multiplicação, divisão e resto (eles têm a mesma precedência).
* Adição e subtração (eles têm a mesma precedência).
* Comparações — mas atenção!
* Operadores lógicos `&&` e `||` — mas atenção!
* Expressão condicional com `?` e `:`.
* Atribuições.
* Execução sequencial (o operador vírgula, `,`).

Duas das linhas na lista acima dizem "mas atenção!" Isso significa que a linha cobre operadores com precedência sutilmente diferente. Nunca dependa da gramática de C para decidir como duas comparações se aninham; em vez disso, sempre use parênteses para especificar o aninhamento.

Você pode deixar vários operadores `&&` ou `||` se associarem, mas sempre use parênteses para mostrar como `&&` e `||` se aninham entre si. Veja [Operadores Lógicos](expressoes-de-controle-de-execucao/operadores-logicos.md).

Há uma outra ordem de precedência da qual o código pode depender:

* Operadores unários pós-fixados.
* Operadores bit-a-bit e de deslocamento — mas atenção!
* Expressão condicional com `?` e `:`.

A advertência para operadores bit-a-bit e de deslocamento é similar à dos operadores lógicos: você pode deixar múltiplos usos de um operador bit-a-bit se associarem, mas sempre use parênteses para controlar o aninhamento de operadores diferentes.

Essas listas não especificam qualquer ordem de precedência entre os operadores bit-a-bit e de deslocamento da segunda lista e os operadores binários acima das expressões condicionais na primeira lista. Quando eles aparecem juntos, coloque parênteses. Veja [Operações Bit-a-bit](aritmetica/operacoes-bit-a-bit.md).

> Nota pessoal de Richard Stallman: Eu escrevi o GCC sem lembrar nada sobre a ordem de precedência em C além do que está declarado aqui. Estudei a tabela completa de precedência para escrever o _parser_ do GCC e prontamente a esqueci novamente. Se você precisar consultar a ordem completa de precedência para entender algum código em C, adicione parênteses suficientes para que ninguém mais precise fazer isso.

