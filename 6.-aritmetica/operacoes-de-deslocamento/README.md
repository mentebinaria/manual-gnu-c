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

# Operações de Deslocamento

Deslocar um inteiro significa mover os valores dos bits para a esquerda ou para a direita dentro dos bits do tipo de dado. O deslocamento é definido apenas para inteiros. Aqui está a forma de escrever:

```c
/* Deslocamento à esquerda.  */
5 << 2 ⇒ 20

/* Deslocamento à direita.  */
5 >> 2 ⇒ 1
```

O operando à esquerda é o valor a ser deslocado, e o operando à direita indica quantos bits deslocá-lo (a contagem de deslocamento). O operando à esquerda é promovido (veja [Promoções de Operando](#user-content-fn-1)[^1]), então o deslocamento nunca opera em um tipo de inteiro estreito; é sempre `int` ou mais amplo. O resultado da operação de deslocamento tem o mesmo tipo que o operando esquerdo promovido.

[^1]: Capítulo pendente de tradução
