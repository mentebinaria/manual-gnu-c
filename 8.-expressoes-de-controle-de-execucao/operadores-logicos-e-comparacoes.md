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

# Operadores Lógicos e Comparações

A coisa mais comum a se usar dentro dos operadores lógicos é uma comparação. Convenientemente, ‘&&’ e ‘||’ têm precedência mais baixa do que os operadores de comparação e operadores aritméticos, então podemos escrever expressões assim, sem parênteses, e obter o aninhamento que é natural: duas operações de comparação que devem ser ambas verdadeiras.

```c
if (r != 0 && x % r == 0)
```

Este exemplo também mostra como é útil que ‘&&’ garanta pular o operando à direita se o operando à esquerda for falso. Por causa disso, esse código nunca tenta dividir por zero.

Isto é equivalente:

```c
if (r && x % r == 0)
```

Um valor verdade é simplesmente um número, então usar `r` como valor verdade testa se ele é diferente de zero. Mas o significado de `r` como uma expressão não é um valor verdade — é um número a ser usado na divisão. Portanto, é mais estiloso escrever explicitamente `!= 0`.

Aqui está outra maneira equivalente de escrever isso:

```c
if (!(r == 0) && x % r == 0)
```

Isso ilustra o operador unário ‘!’, e a necessidade de escrever parênteses ao redor de seu operando.
