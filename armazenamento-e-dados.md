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

# 👜 Armazenamento e Dados

O armazenamento em programas C é composto por unidades chamadas _bytes_. Um byte é a menor unidade de armazenamento que pode ser usada primariamente.

Em quase todos os computadores, um byte é composto por 8 bits. Existem alguns computadores peculiares (principalmente “controladores embarcados” para sistemas muito pequenos) onde um byte é maior do que isso, mas este manual não tenta explicar a peculiaridade desses computadores; assumimos que um byte tem 8 bits.

Cada tipo de dado em C é composto por um certo número de bytes; esse número é o tamanho do tipo de dado. Veja [Tamanho do Tipo](#user-content-fn-1)[^1], para mais detalhes. Os tipos `signed char` e `unsigned char` têm um byte de comprimento; use esses tipos para operar com dados byte a byte. Veja [Tipos Com e Sem Sinal](#user-content-fn-2)[^2]. Você pode se referir a uma série de bytes consecutivos como um array de elementos `char`; é assim que uma string de caracteres se parece na memória. Veja [Strings Constantes](#user-content-fn-3)[^3].

[^1]: Capítulo pendente de tradução

[^2]: Capítulo pendente de tradução

[^3]: Capítulo pendente de tradução
