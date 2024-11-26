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

# Aritmética Básica

A aritmética básica em C é feita com os operadores binários usuais da álgebra: adição (‘+’), subtração (‘-’), multiplicação (‘\*’) e divisão (‘/’). O operador unário ‘-’ é usado para mudar o sinal de um número. O operador unário `+` também existe; ele retorna seu operando inalterado.

‘/’ é o operador de divisão, mas dividir inteiros pode não dar o resultado que você espera. Seu valor é um inteiro, que não é igual ao quociente matemático quando este é uma fração. Use ‘%’ para obter o resto inteiro correspondente, quando necessário. Veja [Divisão e Resto](#user-content-fn-1)[^1]. A divisão de ponto flutuante produz um valor o mais próximo possível do quociente matemático.

Esses operadores usam a sintaxe algébrica com a regra de precedência algébrica usual (veja [Gramática de Operadores Binários](#user-content-fn-2)[^2]) de que multiplicação e divisão são feitas antes de adição e subtração, mas você pode usar parênteses para especificar explicitamente como os operadores devem se aninhar. Eles são associativos à esquerda (veja[ Associatividade e Ordenação](#user-content-fn-3)[^3]). Assim,

```c
-a + b - c + d * e / f
```

é equivalente a

```c
(((-a) + b) - c) + ((d * e) / f)
```

[^1]: Capítulo pendente de tradução

[^2]: Capítulo pendente de tradução

[^3]: Capítulo pendente de tradução
