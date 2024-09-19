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

# Escreva Atribuições em Instruções Separadas

É frequentemente conveniente escrever uma atribuição dentro de uma condição `if`, mas isso pode reduzir a legibilidade do programa. Aqui está um exemplo do que evitar:

```c
if (x = advance (x))
  …
```

A ideia aqui é avançar `x` e testar se o valor é diferente de zero. No entanto, os leitores podem não perceber que está sendo usado ‘=’ e não ‘==’. De fato, escrever ‘=’ onde ‘==’ era pretendido dentro de uma condição é um erro comum, por isso o GNU C pode emitir avisos quando ‘=’ aparece de uma forma que sugere ser um erro.

É muito mais claro escrever a atribuição como uma instrução separada, assim:

```c
x = advance (x);
if (x != 0)
  …
```

Isso torna inconfundivelmente claro que `x` está recebendo um novo valor.

Outro método é usar o operador vírgula (veja [Operador Vírgula](#user-content-fn-1)[^1]), assim:

```c
if (x = advance (x), x != 0)
  …
```

No entanto, colocar a atribuição em uma instrução separada geralmente é mais claro, a menos que a atribuição seja muito curta, pois isso reduz o aninhamento.

[^1]: Capítulo pendente de tradução
