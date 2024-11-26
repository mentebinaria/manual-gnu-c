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

# Reordenação de Operandos

A linguagem C não garante que as operações dentro de uma expressão sejam realizadas na ordem em que aparecem no código. Por exemplo, na expressão:

```c
foo () + bar ()
```

`foo` pode ser chamada primeiro ou `bar` pode ser chamada primeiro. Se `foo` atualiza um dado e `bar` usa esse dado, os resultados podem ser imprevisíveis.

A ordem imprevisível de cálculo de subexpressões também faz diferença quando uma delas contém uma atribuição. Já vimos este exemplo de código problemático:

```c
x = 20;
printf ("%d %d\n", x, x = 4);
```

Nesse caso, o segundo argumento, `x`, pode ter um valor diferente dependendo se ele for computado antes ou depois da atribuição no terceiro argumento.
