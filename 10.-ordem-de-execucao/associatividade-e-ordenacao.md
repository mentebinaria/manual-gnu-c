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

# Associatividade e Ordenação

Um operador binário associativo, como `+`, quando usado repetidamente, pode combinar qualquer número de operandos. Os valores dos operandos podem ser calculados em qualquer ordem.

Se os valores forem inteiros e o estouro puder ser ignorado, eles podem ser combinados em qualquer ordem. Assim, dadas quatro funções que retornam `unsigned int`, chamá-las e somar seus resultados, como no exemplo:

```c
(foo () + bar ()) + (baz () + quux ())
```

pode somar os resultados em qualquer ordem.

Por outro lado, a aritmética com inteiros com sinal, em que o estouro é significativo, nem sempre é associativa (veja [Estouro de Inteiros](../6.-aritmetica/estouro-de-inteiros/)). Portanto, as somas devem ser realizadas na ordem especificada, obedecendo os parênteses e a associação à esquerda. Isso significa calcular `(foo () + bar ())` e `(baz () + quux ())` primeiro (em qualquer ordem), depois somar os dois.

O mesmo se aplica à aritmética com valores de ponto flutuante, já que ela também não é realmente associativa. No entanto, a opção do GCC `-funsafe-math-optimizations` permite que o compilador altere a ordem de cálculo quando uma operação associativa (associativa na matemática exata) combina vários operandos. Essa opção entra em vigor ao compilar um módulo (veja Compilação[^1]). Alterar a ordem de associação pode permitir que o programa otimize a execução das operações de ponto flutuante.

Em todos esses casos, as quatro chamadas de função podem ser realizadas em qualquer ordem. Não há certo ou errado nisso.

[^1]: **Capítulo pendente de tradução**
