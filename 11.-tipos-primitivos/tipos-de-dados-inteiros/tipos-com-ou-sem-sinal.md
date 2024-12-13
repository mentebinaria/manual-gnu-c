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

# Tipos Com ou Sem Sinal

Um tipo inteiro **sem sinal** pode representar apenas números positivos e zero. Um tipo **com sinal** pode representar tanto números positivos quanto negativos, em um intervalo distribuído quase igualmente em ambos os lados do zero. Por exemplo, `unsigned char` armazena números de 0 a 255 (na maioria dos computadores), enquanto `signed char` armazena números de -128 a 127. Cada um desses tipos possui 256 valores possíveis, já que ambos ocupam 8 bits.

Escreva `signed` ou `unsigned` antes da palavra-chave do tipo para especificar se o tipo é com ou sem sinal. No entanto, os tipos inteiros diferentes de `char` são, por padrão, **com sinal**; com eles, `signed` é um termo redundante.

O `char` simples pode ser **com sinal** ou **sem sinal**; isso depende do compilador, da máquina em uso e do sistema operacional.

Em muitos programas, não faz diferença se `char` é com ou sem sinal. Quando isso for relevante, não deixe ao acaso; escreva explicitamente `signed char` ou `unsigned char`.

***

**Nota pessoal de Richard Stallman**: Uma vez comendo com hackers em um restaurante de peixes, pedi um prato chamado _Arctic Char_. Quando minha refeição chegou, notei que o chef não a havia assinado. Então reclamei: "Este char está sem sinal—eu queria um char com sinal!" Ou, melhor, teria dito isso se tivesse pensado rápido o suficiente.

{% hint style="info" %}
A piada acima funciona em inglês porque, em inglês, "_signed"_ também significa "assinado" e no mundo da gastronomia existem os pratos assinados, de chefs famosos/as, etc.
{% endhint %}
