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

# Estouro de Inteiro

Quando o valor matemático de uma operação aritmética não cabe no intervalo do tipo de dado em uso, isso é chamado de estouro (_overflow_, em inglês). Quando isso ocorre na aritmética de inteiros, é chamado de estouro de inteiros.

O estouro de inteiros acontece apenas em operações aritméticas. Operações de conversão de tipo, por definição, não causam estouro, mesmo quando o resultado não cabe em seu novo tipo. [Veja Conversão de Inteiros](#user-content-fn-1)[^1].

Números com sinal usam a representação em complemento de dois, na qual o número mais negativo não tem um equivalente positivo (veja [Inteiros em Detalhe](#user-content-fn-2)[^2]). Assim, o operador unário ‘-’ em um inteiro com sinal pode causar estouro.

[^1]: Capítulo pendente de tradução

[^2]: Capítulo pendente de tradução
