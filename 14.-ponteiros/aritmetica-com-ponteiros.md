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

# Aritmética com Ponteiros

Somar um inteiro (positivo ou negativo) a um ponteiro é válido em C. Isso assume que o ponteiro aponta para um elemento de um array, e **avança ou recua** o ponteiro o número de elementos indicado pelo inteiro. Aqui está um exemplo em que somar um inteiro positivo **avança** o ponteiro para elementos posteriores do mesmo array:

```c
void
incrementing_pointers()
{
  int array[5] = { 45, 29, 104, -3, 123456 };
  int elt0, elt1, elt4;

  int *p = &array[0];
  /* Agora p aponta para o elemento 0. Busque o valor. */
  elt0 = *p;

  ++p;
  /* Agora p aponta para o elemento 1. Busque o valor. */
  elt1 = *p;

  p += 3;
  /* Agora p aponta para o elemento 4 (o último). Busque o valor. */
  elt4 = *p;

  printf("elt0 %d  elt1 %d  elt4 %d.\n", elt0, elt1, elt4);
  /* Imprime: elt0 45  elt1 29  elt4 123456. */
}
```

Abaixo, um exemplo em que somar um inteiro **negativo recua** o ponteiro para elementos anteriores do array:

```c
void
decrementing_pointers()
{
  int array[5] = { 45, 29, 104, -3, 123456 };
  int elt0, elt3, elt4;

  int *p = &array[4];
  /* Agora p aponta para o elemento 4 (o último). Busque o valor. */
  elt4 = *p;

  --p;
  /* Agora p aponta para o elemento 3. Busque o valor. */
  elt3 = *p;

  p -= 3;
  /* Agora p aponta para o elemento 0. Busque o valor. */
  elt0 = *p;

  printf("elt0 %d  elt3 %d  elt4 %d.\n", elt0, elt3, elt4);
  /* Imprime: elt0 45  elt3 -3  elt4 123456. */
}
```

Se um valor de ponteiro foi criado somando um inteiro a outro ponteiro, deve ser possível subtrair esses dois ponteiros e obter novamente o inteiro original. Isso também funciona em C:

```c
void
subtract_pointers()
{
  int array[5] = { 45, 29, 104, -3, 123456 };
  int *p0, *p3, *p4;

  int *p = &array[4];
  /* Agora p aponta para o elemento 4 (último). Guarde o valor. */
  p4 = p;

  --p;
  /* Agora p aponta para o elemento 3. Guarde o valor. */
  p3 = p;

  p -= 3;
  /* Agora p aponta para o elemento 0. Guarde o valor. */
  p0 = p;

  printf("%d, %d, %d, %d\n",
         p4 - p0, p0 - p0, p3 - p0, p0 - p3);
  /* Imprime: 4, 0, 3, -3. */
}
```

A operação de soma **não sabe onde começam ou terminam os arrays na memória**. Tudo o que ela faz é somar o inteiro (multiplicado pelo tamanho do tipo apontado) ao valor numérico do ponteiro. Quando o ponteiro original e o resultado apontam para dentro do mesmo array, o resultado é **bem definido**.

{% hint style="danger" %}
Somente programadores/as experientes devem fazer aritmética com ponteiros envolvendo objetos de memória diferentes.
{% endhint %}

O resultado da subtração entre dois ponteiros tem tipo `int` ou `long` se necessário (veja [_Tipos de Dados Inteiros_](../11.-tipos-primitivos/tipos-de-dados-inteiros/)). A forma limpa de declarar esse tipo é usando o tipo `ptrdiff_t`, definido no arquivo `<stddef.h>`.

O C define a subtração de ponteiros de forma a ser **consistente com a adição ponteiro + inteiro**, de modo que `(p3 - p1) + p1` seja igual a `p3`, como em álgebra comum. A subtração entre ponteiros funciona subtraindo o valor numérico de `p1` de `p3`, e dividindo pelo **tamanho do tipo apontado**. Os dois ponteiros devem apontar para dentro do **mesmo array**.

No C padrão, **adições e subtrações não são permitidas com `void *`**, já que o tamanho do tipo apontado não está definido nesse caso. O mesmo vale para **ponteiros para funções**. No entanto, essas operações funcionam no **GNU C**, e o "tamanho do tipo apontado" é considerado como **1 byte**.
