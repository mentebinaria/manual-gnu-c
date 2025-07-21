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

# Tipos de Ponteiros

Para cada tipo de dado `t`, existe um tipo para ponteiros para o tipo `t`. Para estas variáveis:

```c
int i;
double a[5];
```

* `i` tem tipo `int`; dizemos que `&i` é um “ponteiro para `int`”.
* `a` tem tipo `double[5]`; dizemos que `&a` é um “ponteiro para um array de cinco `double`s”.
* `a[3]` tem tipo `double`; dizemos que `&a[3]` é um “ponteiro para `double`”.
