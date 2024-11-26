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

# Otimização e Ordenação

Os pontos de sequência limitam a liberdade do compilador para reordenar operações arbitrariamente, mas as otimizações ainda podem reordená-las se o compilador concluir que isso não alterará os resultados. Assim, neste código:

```c
x++;
y = z;
x++;
```

há um ponto de sequência após cada instrução, então o código deve incrementar `x` uma vez antes da atribuição a `y` e outra vez depois. No entanto, o incremento de `x` não afeta `y` ou `z`, e a definição de `y` não pode afetar `x`. Por isso, o código pode ser otimizado para:

```c
y = z;
x += 2;
```

Normalmente, isso não tem nenhum efeito além de tornar o programa mais rápido. Mas existem situações especiais em que isso pode causar problemas devido a coisas que o compilador não pode saber, como memória compartilhada. Para limitar a otimização nesses casos, use o qualificador de tipo `volatile` (veja volatile[^1]).

[^1]: Pendente de tradução
