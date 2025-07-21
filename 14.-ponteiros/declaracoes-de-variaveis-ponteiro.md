---
layout:
  width: default
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
  metadata:
    visible: true
---

# Declarações de Variáveis Ponteiro

A forma de declarar que uma variável `foo` aponta para o tipo `t` é:

```c
t *foo;
```

Para lembrar essa sintaxe, pense: “se você desreferenciar `foo`, usando o operador ‘\*’, o que você obtém é do tipo `t`. Logo, `foo` aponta para o tipo `t`.”

Assim, podemos declarar variáveis que armazenam ponteiros para esses três tipos, da seguinte maneira:

```c
int *ptri;            /* Ponteiro para int. */
double *ptrd;         /* Ponteiro para double. */
double (*ptrda)[5];   /* Ponteiro para double[5]. */
```

A declaração `int *ptri;` significa: “se você desreferenciar `ptri`, obtém um `int`.” Já `double (*ptrda)[5];` significa: “se você desreferenciar `ptrda`, e então indexar por um inteiro menor que 5, você obtém um `double`.” Os parênteses expressam o fato de que você deve desreferenciar primeiro, depois indexar.

Compare isso com a seguinte declaração:

```c
double *aptrd[5];     /* Array de cinco ponteiros para double. */
```

Como o operador ‘\*’ tem precedência sintática menor que a indexação, `double *aptrd[5]` significa: “se você indexar `aptrd` por um inteiro menor que 5, e então desreferenciar, obtém um `double`.” Portanto, `*aptrd[5]` declara um array de ponteiros, não um ponteiro para array.
