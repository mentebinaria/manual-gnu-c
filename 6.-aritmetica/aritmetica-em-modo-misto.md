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

# Aritmética em Modo Misto

Misturar inteiros e números de ponto flutuante em uma operação aritmética básica converte automaticamente os inteiros para ponto flutuante. Na maioria dos casos, isso dá exatamente os resultados desejados. Mas, às vezes, importa exatamente onde a conversão ocorre.

Se `i` e `j` são inteiros, `(i + j) * 2.0` os adiciona como inteiros e, em seguida, converte a soma para ponto flutuante para a multiplicação. Se a adição causar um estouro, isso não é equivalente a converter cada inteiro para ponto flutuante e, em seguida, somar os dois números de ponto flutuante. Você pode obter este último resultado convertendo explicitamente os inteiros, como em `((double) i + (double) j) * 2.0`. Veja [Conversão Explícita de Tipo](#user-content-fn-1)[^1].

Somar ou multiplicar vários valores, incluindo alguns inteiros e alguns de ponto flutuante, realiza as operações da esquerda para a direita. Assim, `3.0 + i + j` converte `i` para ponto flutuante, depois adiciona `3.0`, depois converte `j` para ponto flutuante e adiciona isso. Você pode especificar uma ordem diferente usando parênteses: `3.0 + (i + j)` soma `i` e `j` primeiro e depois adiciona essa soma (convertida para ponto flutuante) a `3.0`. Nesse aspecto, C difere de outras linguagens, como Fortran.

[^1]: Capítulo pendente de tradução
