---
layout:
  width: default
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
  metadata:
    visible: true
---

# Conversão entre Ponteiros e Inteiros

Em computadores modernos, um endereço de memória é simplesmente um **número**. Ele ocupa o mesmo espaço que um inteiro de determinado tamanho. Em C, você pode **converter um ponteiro para tipos inteiros apropriados e vice-versa**, **sem perder informação**.

Os tipos inteiros apropriados para isso são:

* `uintptr_t` — tipo **sem sinal**;
* `intptr_t` — tipo **com sinal**.

Ambos são definidos no cabeçalho `<stdint.h>`.

***

**Exemplo:**

```c
#include <stdint.h>
#include <stdio.h>

void
print_pointer(void *ptr)
{
  uintptr_t converted = (uintptr_t) ptr;

  printf("Pointer value is 0x%x\n", (unsigned int) converted);
}
```

A especificação `%x` no _template_ da `printf` indica que o valor será impresso em **notação hexadecimal**.

É mais limpo usar `uintptr_t`, já que a impressão hexadecimal trata o número como **sem sinal**, mas na prática isso **não faz diferença**: o que a `printf` recebe é apenas a sequência de bits do número.

{% hint style="danger" %}
Converter ponteiros para inteiros é arriscado — não faça isso, a menos que seja realmente necessário.
{% endhint %}
