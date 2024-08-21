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

# Estouro com Inteiros sem Sinal

A aritmética sem sinal em C ignora o estouro; ela produz o resultado real módulo a enésima potência de 2, onde n é o número de bits no tipo de dado. Dizemos que ela “trunca” o resultado verdadeiro para os n bits mais baixos.

{% hint style="info" %}
No parágrafo acima, a palavra módulo significa o operador matemático de cálculo do resto, que em C é representado pelo caractere %. A expressão neste caso poderia ser representada por **resultado\_real % pow(2, 32)**, para um inteiro de 32 bits.
{% endhint %}

Um resultado real que é negativo, quando tomado módulo a enésima potência de 2, gera um número positivo. Por exemplo,

```c
unsigned int x = 1;
unsigned int y;

y = -x;
```

causa estouro porque o número negativo -1 não pode ser armazenado em um tipo sem sinal. O resultado real, que é -1 módulo a enésima potência de 2, é um a menos que a enésima potência de 2. Esse é o maior valor que o tipo de dado sem sinal pode armazenar. Para um `unsigned int` de 32 bits, o valor é 4.294.967.295. Veja [Valores Máximos e Mínimos](#user-content-fn-1)[^1].

Adicionar esse número a si mesmo, como aqui,

```c
unsigned int z;

z = y + y;
```

deveria gerar 8.489.934.590; no entanto, isso novamente é grande demais para caber, então o estouro trunca o valor para 4.294.967.294. Se fosse um inteiro com sinal, isso significaria -2, o que (não por coincidência) é igual a -1 + -1.

[^1]: Capítulo pendente de tradução
