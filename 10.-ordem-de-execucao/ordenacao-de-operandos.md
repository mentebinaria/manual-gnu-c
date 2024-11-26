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

# Ordenação de Operandos

Os operandos e argumentos podem ser computados em qualquer ordem, mas há limites para esse embaralhamento no GNU C:

* **Operandos de um operador aritmético binário** podem ser computados em qualquer ordem, mas não podem ser misturados: um deles precisa ser completamente calculado antes do outro. Quaisquer efeitos colaterais no operando que é computado primeiro são executados antes que o outro operando seja computado.
* Isso também se aplica aos operadores de atribuição, exceto na atribuição simples, onde o valor anterior do operando à esquerda não é utilizado.
* **Os argumentos em uma chamada de função** podem ser computados em qualquer ordem, mas também não podem ser misturados. Assim, um argumento é totalmente calculado, depois outro, e assim por diante, até que todos sejam concluídos. Quaisquer efeitos colaterais em um argumento são executados antes que a computação de outro argumento comece.

Essas regras não cobrem os efeitos colaterais causados pelos operadores de pós-incremento e pós-decremento — esses podem ser adiados até o próximo ponto de sequência.

Se quisermos ser rigorosos, o fato é que o GCC pode reordenar os cálculos de muitas outras maneiras, desde que isso não altere o resultado da execução do programa. No entanto, porque isso não altera o resultado do programa, é algo desprezível, a menos que você esteja preocupado com os valores de certas variáveis em determinados momentos vistos por outros processos. Nesses casos, você deve usar `volatile` para evitar otimizações que poderiam fazer com que se comportassem de maneira estranha. Veja volatile[^1].

[^1]: **Otimização e Ordenação**
