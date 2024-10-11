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

# Operadores Lógicos e Atribuições

Existem casos em que atribuições aninhadas dentro de uma condição podem realmente tornar um programa mais fácil de ler. Aqui está um exemplo usando um tipo hipotético `list` que representa uma lista; ele testa se a lista tem pelo menos dois elementos, utilizando funções hipotéticas, `nonempty`, que retorna verdadeiro se o argumento for uma lista não vazia, e `list_next`, que avança de um elemento da lista para o próximo. Assumimos que uma lista nunca é um ponteiro nulo, de modo que as expressões de atribuição são sempre “verdadeiras.”

```c
if (nonempty (list)
    && (temp1 = list_next (list))
    && nonempty (temp1)
    && (temp2 = list_next (temp1)))
  …  /* usa temp1 e temp2 */
```

Aqui aproveitamos o operador ‘&&’ para evitar a execução do restante do código se uma chamada a `nonempty` retornar “falso.” O único lugar natural para colocar as atribuições é entre essas chamadas.

Seria possível reescrever isso como várias instruções, mas isso poderia tornar o código muito mais pesado. Por outro lado, quando o teste é ainda mais complexo do que este, dividi-lo em várias instruções pode ser necessário para manter a clareza.

Se uma lista vazia for um ponteiro nulo, podemos dispensar a chamada a `nonempty`:

```c
if ((temp1 = list_next (list))
    && (temp2 = list_next (temp1)))
  …
```
