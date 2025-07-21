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

# Desreferenciando Ponteiros Nulos ou Inválidos

Tentar desreferenciar um **ponteiro nulo** é um erro. Na maioria das plataformas, isso geralmente causa um **sinal**, normalmente `SIGSEGV` (veja [_Sinais_](#user-content-fn-1)[^1]).

```c
char *foo = NULL;
c = *foo;    /* Isso causa um sinal e termina o programa. */
```

O mesmo ocorre com um ponteiro que possui **alinhamento incorreto** para o tipo de dado apontado (em muitos tipos de computadores), ou que aponta para uma parte da memória **não alocada** no espaço de endereçamento do processo.

Esse sinal termina o programa, **a menos que** ele tenha sido configurado para lidar com o sinal (veja [_The GNU C Library_](https://www.gnu.org/software/libc/manual/html_node/Signal-Handling.html#Signal-Handling) em _The GNU C Library Reference Manual_).

No entanto, o sinal pode **não ocorrer** se a desreferência for **eliminada pela otimização**. No exemplo acima, se você não usar posteriormente o valor de `c`, o GCC pode otimizar e remover o código de `*foo`. Para evitar esse tipo de otimização, você pode usar o qualificador `volatile`, como neste exemplo:

```c
volatile char *p;
volatile char c;
c = *p;
```

Você pode usar isso para testar se `p` aponta para memória não alocada. Basta configurar primeiro um **tratador de sinal**, para que o sinal não termine o programa.

[^1]: Apêndice pendente de tradução
