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

# Inteiros Estreitos

Os tipos que são mais estreitos que `int` raramente são usados para variáveis comuns — em vez disso, usamos `int`. Isso ocorre porque C converte esses tipos mais estreitos para `int` em qualquer operação aritmética. Literalmente, não há razão para declarar uma variável local como `char`, por exemplo.

Particularmente, se o valor for realmente um caractere, você deve declarar a variável como `int`. **Não como `char`!** Usar esse tipo estreito pode forçar o compilador a truncar valores durante a conversão, o que é um desperdício. Além disso, algumas funções retornam um valor de caractere ou `-1` para indicar "nenhum caractere". Usar `int` permite distinguir `-1` de um caractere pelo sinal.

Os tipos inteiros estreitos são úteis como partes de outros objetos, como arrays e estruturas. Compare estas declarações de arrays, cujos tamanhos em processadores de 32 bits são mostrados:

```c
signed char ac[1000];   /* 1000 bytes */
short as[1000];         /* 2000 bytes */
int ai[1000];           /* 4000 bytes */
long long all[1000];    /* 8000 bytes */
```

Além disso, cadeias de caracteres (_strings_) devem ser compostas por `char`, porque é isso que todas as funções padrão da biblioteca esperam. Assim, o array `ac` poderia ser usado como uma cadeia de caracteres, mas os outros não.
