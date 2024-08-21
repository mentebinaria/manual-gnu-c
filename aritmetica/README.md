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

# ➕ Aritmética

Os operadores aritméticos em C tentam ser o mais semelhante possível às operações aritméticas abstratas, mas é impossível fazer isso de forma perfeita. Números em um computador têm um intervalo finito de valores possíveis, e valores não inteiros têm um limite em sua precisão possível. No entanto, exceto quando os resultados estão fora do intervalo, você não terá surpresas ao usar ‘+’ para adição, ‘-’ para subtração e ‘\*’ para multiplicação.

Cada operador em C tem uma precedência, que é sua posição na ordem gramatical dos vários operadores. Os operadores com a maior precedência capturam os operandos adjacentes primeiro; essas expressões então se tornam operandos para operadores de menor precedência. Damos algumas informações sobre a precedência dos operadores neste capítulo onde descrevemos os operadores; para a explicação completa, veja [Gramática de Operadores Binários](#user-content-fn-1)[^1].

Os operadores aritméticos sempre promovem seus operandos antes de operar sobre eles. Isso significa converter tipos de dados inteiros estreitos para um tipo de dado mais amplo (veja [Promoções de Operando](#user-content-fn-2)[^2]). Se você está apenas começando a aprender C, não se preocupe com isso ainda.

Dado dois operandos que têm tipos diferentes, a maioria das operações aritméticas os converte para um tipo comum. Por exemplo, se um dado é `int` e o outro é `double`, o tipo comum é `double`. (Isso ocorre porque `double` pode representar todos os valores que um `int` pode conter, mas o contrário não é verdadeiro.) Para mais detalhes, veja [Tipo Comum](#user-content-fn-3)[^3].

[^1]: Capítulo pendente de tradução

[^2]: Capítulo pendente de tradução

[^3]: Capítulo pendente de tradução
