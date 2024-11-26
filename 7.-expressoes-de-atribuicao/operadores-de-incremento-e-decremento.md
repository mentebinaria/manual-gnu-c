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

# Operadores de Incremento e Decremento

Os operadores ‘++’ e ‘--’ são os operadores de incremento e decremento. Quando usados em um valor numérico, eles adicionam ou subtraem 1. Não os consideramos como atribuições, mas eles são equivalentes a atribuições.

Usar ‘++’ ou ‘--’ como prefixo, antes de um _lvalue_, é chamado de pré-incremento ou pré-decremento. Isso adiciona ou subtrai 1, e o resultado se torna o valor da expressão. Por exemplo,

```c
#include <stdio.h>   /* Declara printf. */

int
main (void)
{
  int i = 5;
  printf ("%d\n", i);
  printf ("%d\n", ++i);
  printf ("%d\n", i);
  return 0;
}
```

imprime linhas contendo 5, 6 e novamente 6. A expressão `++i` incrementa `i` de 5 para 6 e tem o valor 6, então a saída do `printf` nessa linha exibe ‘6’.

Usando ‘--’ em vez disso, para pré-decremento,

```c
#include <stdio.h>   /* Declara printf. */

int
main (void)
{
  int i = 5;
  printf ("%d\n", i);
  printf ("%d\n", --i);
  printf ("%d\n", i);
  return 0;
}
```

imprime três linhas que contêm (respectivamente) ‘5’, ‘4’ e novamente ‘4’.
