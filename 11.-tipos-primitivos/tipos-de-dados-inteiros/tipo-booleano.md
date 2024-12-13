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

# Tipo Booleano

O tipo inteiro sem sinal `bool` armazena valores verdade: seus possíveis valores são 0 e 1. Converter qualquer valor diferente de zero para `bool` resulta em 1. Por exemplo:

```c
bool a = 0;
bool b = 1;
bool c = 4; /* Armazena o valor 1 em c. */
```

Diferentemente de `int`, `bool` não é uma palavra-chave. Ele é definido no arquivo de cabeçalho `stdbool.h`.

{% hint style="info" %}
Na história das especificações de C, a palavra-chave `_Bool` foi introduzida na C99, junto com o arquivo de cabeçalho mencionado no texto. Isso significa que você pode usar uma variável do tipo `_Bool` e atribuir a ela os valores 0 ou 1. Alternativamente, você pode incluir o cabeçalho `stdbool.h` e usar `bool` junto a `true` ou `false`. No entanto, a partir da C23, `bool` é uma palavra-chave e não necessita de arquivos de cabeçalho adicionais, mas o suporte a esta especificação ainda pode ser parcial em alguns compiladores.
{% endhint %}

