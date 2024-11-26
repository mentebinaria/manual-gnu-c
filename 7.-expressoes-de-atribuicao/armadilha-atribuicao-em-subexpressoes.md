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

# Armadilha: Atribuição em Subexpressões

Em C, a ordem de cálculo das partes de uma expressão não é fixa. Com exceção de alguns poucos casos especiais, as operações podem ser calculadas em qualquer ordem. Se uma parte da expressão tem uma atribuição para `x` e outra parte da expressão usa `x`, o resultado é imprevisível, pois esse uso pode ser calculado antes ou depois da atribuição.

Aqui está um exemplo de código ambíguo:

```c
x = 20;
printf ("%d %d\n", x, x = 4);
```

Se o segundo argumento, `x`, for calculado antes do terceiro argumento, `x = 4`, o valor do segundo argumento será 20. Se eles forem calculados na outra ordem, o valor do segundo argumento será 4.

Aqui está uma maneira de tornar esse código não ambíguo:

```c
y = 20;
printf ("%d %d\n", y, x = 4);
```

Aqui está outra maneira, com o outro significado:

```c
x = 4;
printf ("%d %d\n", x, x);
```

Esse problema se aplica a todos os tipos de atribuições, e aos operadores de incremento e decremento, que são equivalentes a atribuições. Veja [Ordem de Execução](#user-content-fn-1)[^1] para mais informações sobre isso.

No entanto, pode ser útil escrever atribuições dentro de uma condição `if` ou um teste `while`, junto com operadores lógicos. Veja [Operadores Lógicos e Atribuições](#user-content-fn-2)[^2].

[^1]: Capítulo pendente de tradução

[^2]: Capítulo pendente de tradução
