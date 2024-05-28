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

# Exemplo de um Programa Completo

Aqui está um exemplo de um programa completo que usa uma versão simples, recursiva, da função `fib` (ver [Fibonacci Recursiva](../o-primeiro-exemplo/fibonacci-recursivo/)):

```c
#include <stdio.h>

int
fib (int n)
{
  if (n <= 2)  /* Isto evita recursividade infinita. */
    return 1;
  else
    return fib (n - 1) + fib (n - 2);
}

int
main (void)
{
  printf ("Fibonacci series item %d is %d\n",
          20, fib (20));
  return 0;
}
```

Este programa imprime uma mensagem que exibe o valor de `fib (20)`.

Agora vamos à uma explicação deste código.
