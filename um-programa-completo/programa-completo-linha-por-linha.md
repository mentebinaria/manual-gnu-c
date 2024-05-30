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

# Programa Completo Linha por Linha

Aqui está o mesmo exemplo explicado linha por linha. **Iniciantes, vocês acham que esta seção ajuda ou não? Vocês gostariam de um **_**layout**_** diferente por exemplo? Por favor, escreva para rms@gnu.org (em inglês).**

```c
#include <stdio.h>      /* Inclui as declarações de funções */
                        /*   de E/S comuns como a printf.  */
                        /* A maiora dos programas precisa delas.  */

int                     /* Essa função retorna um int.  */
fib (int n)             /* O nome dela é fib;  */
                        /*   seu argumento é o n.  */
{                       /* Início do corpo da função.  */
  /* Evita que a recursão seja inifinta.  */
  if (n <= 2)           /* Se n é 1 ou 2,  */
    return 1;           /*   faça com que fib retorne 1.  */
  else                  /* do contrário, some os dois números  */
                        /* Fibonacci anteriores.  */
    return fib (n - 1) + fib (n - 2);
}

int                     /* Essa função retorna um int.  */
main (void)             /* Comece aqui; ignore os argumentos.  */
{                       /* Imprima a mensagem com os números.  */
  printf ("Fibonacci series item %d is %d\n",
          20, fib (20));
  return 0;             /* Termine programa, reporte successo.  */
}
```
