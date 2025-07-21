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

# Designadores de Tipo de Ponteiro

Todo tipo em C possui um _designador_; você o obtém removendo o nome da variável e o ponto e vírgula de uma declaração (veja [Designadores de Tipos](../11.-tipos-primitivos/designadores-de-tipos.md)). Aqui estão os designadores para os tipos de ponteiros das declarações de exemplo da seção anterior:

```c
int *           /* Ponteiro para int. */
double *        /* Ponteiro para double. */
double (*)[5]   /* Ponteiro para double[5]. */
```

Lembre-se: para entender que tipo um designador representa, imagine a declaração correspondente com um nome de variável inserido, e determine qual seria o tipo dessa variável. Assim, o designador de tipo `double (*)[5]` corresponde à declaração de variável:

```c
double (*variavel)[5];
```

Isso declara uma variável ponteiro que, ao ser desreferenciada, fornece um array de 5 `double`s. Portanto, o designador de tipo significa: “ponteiro para um array de 5 `double`s”.
