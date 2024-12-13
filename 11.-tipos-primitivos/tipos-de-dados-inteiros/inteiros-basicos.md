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

# Inteiros Básicos

Os tipos de dados inteiros em C podem ser **com sinal** ou **sem sinal**. Um tipo **sem sinal** pode representar apenas números positivos e zero. Um tipo **com sinal** pode representar números positivos e negativos, em um intervalo distribuído quase igualmente em ambos os lados do zero.

Além da característica de sinalização, os tipos de dados inteiros variam em **tamanho**, ou seja, no número de bytes que ocupam. O tamanho determina o intervalo de valores inteiros que o tipo pode armazenar.

Aqui está uma lista dos tipos de dados inteiros **com sinal**, com os tamanhos que possuem na maioria dos computadores. Cada um tem um tipo correspondente **sem sinal**; veja [_Tipos Com ou Sem Sinal_](tipos-com-ou-sem-sinal.md).

* **`signed char`**\
  Um byte (8 bits). Este tipo inteiro é usado principalmente para inteiros que representam caracteres, geralmente como elementos de arrays ou campos de outras estruturas de dados.
* **`short`** ou **`short int`**\
  Dois bytes (16 bits).
* **`int`**\
  Quatro bytes (32 bits).
* **`long`** ou **`long int`**\
  Quatro bytes (32 bits) ou oito bytes (64 bits), dependendo da plataforma. Tipicamente, é de 32 bits em computadores de 32 bits e 64 bits em computadores de 64 bits, mas há exceções.
* **`long long`** ou **`long long int`**\
  Oito bytes (64 bits). Suportado no GNU C desde os anos 1980 e incorporado ao padrão C a partir do ISO C99.

Você pode omitir `int` ao usar `long` ou `short`. Isso é inofensivo e uma prática comum.
