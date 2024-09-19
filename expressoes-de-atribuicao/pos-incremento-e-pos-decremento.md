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

# Pós-incremento e Pós-decremento

Usar ‘++’ ou ‘--’ após um _lvalue_ faz algo peculiar: obtém o valor diretamente do _lvalue_ e, em seguida, o incrementa ou decrementa. Assim, o valor de `i++` é o mesmo que o valor de `i`, mas `i++` também incrementa `i` “um pouco depois”. Isso é chamado de pós-incremento ou pós-decremento.

Por exemplo,

```c
#include <stdio.h>   /* Declara printf. */

int
main (void)
{
  int i = 5;
  printf ("%d\n", i);
  printf ("%d\n", i++);
  printf ("%d\n", i);
  return 0;
}
```

imprime linhas contendo 5, novamente 5, e 6. A expressão `i++` tem o valor 5, que é o valor de `i` naquele momento, mas incrementa `i` de 5 para 6 logo em seguida.

O quanto "logo em seguida" acontece? O compilador tem certa flexibilidade para decidir isso. A regra é que o incremento deve ocorrer até o próximo _sequence point_; em casos simples, isso significa até o final da instrução. Veja [Pontos de Sequência](#user-content-fn-1)[^1].

Independentemente de onde exatamente o código compilado incrementa o valor de `i`, o ponto crucial é que o valor de `i++` é o valor que `i` tinha antes de ser incrementado.

Se um operador unário precede uma expressão de pós-incremento ou pós-decremento, o incremento é aninhado internamente:

```c
-a++   é equivalente a   -(a++)
```

Essa é a única ordem que faz sentido; `-a` não é um _lvalue_, então não pode ser incrementado.

O uso mais comum de pós-incremento é com arrays. Aqui está um exemplo de uso de pós-incremento para acessar um elemento de um array e avançar o índice para o próximo acesso. Compare com o exemplo `avg_of_double` (veja [Um Exemplo com Arrays](../alem-dos-inteiros/um-exemplo-com-arrays.md)), que é quase o mesmo, mas não usa pós-incremento.

```c
double
avg_of_double_alt (int length, double input_data[])
{
  double sum = 0;
  int i;

  /* Pega cada elemento e adiciona à soma.  */
  for (i = 0; i < length;)
    /* Usa o índice i, depois o incrementa.  */
    sum += input_data[i++];

  return sum / length;
}
```

[^1]: Capítulo pendente de tradução
