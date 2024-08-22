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

# Comparações Numéricas

Existem dois tipos de operadores de comparação: os de **igualdade** e os de **ordenação**. Comparações de igualdade testam se duas expressões têm o mesmo valor. O resultado é um _valor verdade_: um número que é 1 para "verdadeiro" ou 0 para "falso".

```c
a == b   /* Testa se é igual.  */
a != b   /* Testa se não é igual.  */
```

A comparação de igualdade é escrita como `==` porque `=` simples é o operador de atribuição.

Comparações de ordenação testam qual operando é maior ou menor. Seus resultados são valores  verdade. Estas são as comparações de ordenação em C:

```c
a < b   /* Testa se é menor-que.  */
a > b   /* Testa se é maior-que.  */
a <= b  /* Testa se é menor-ou-igual.  */
a >= b  /* Testa se é maior-ou-igual.  */
```

Para quaisquer inteiros `a` e `b`, exatamente uma das comparações `a < b`, `a == b` e `a > b` é verdadeira, assim como na matemática. No entanto, se `a` e `b` são valores especiais de ponto flutuante (não números ordinários), todas as três podem ser falsas. Veja [Valores Especiais de Ponto Flutuante](#user-content-fn-1)[^1] e [Otimizações Inválidas](#user-content-fn-2)[^2].

[^1]: Capítulo pendente de tradução

[^2]: Capítulo pendente de tradução
