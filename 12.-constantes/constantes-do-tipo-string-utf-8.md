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

# Constantes do Tipo String UTF-8

Escrever ‘u8’ imediatamente antes de uma constante do tipo string, sem espaço intermediário, significa representar essa string na codificação UTF-8 como uma sequência de bytes. O UTF-8 representa caracteres ASCII com um único byte e representa caracteres Unicode não ASCII (códigos 128 e acima) como sequências de múltiplos bytes. Aqui está um exemplo de uma constante do tipo string UTF-8:

```c
u8"A cónstàñt"
```

Essa constante ocupa 13 bytes mais o caractere nulo de terminação, porque cada uma das letras acentuadas é uma sequência de dois bytes.

Concatenar uma string comum com uma string UTF-8 conceitualmente produz outra string UTF-8. No entanto, se a string comum contiver códigos de caracteres 128 ou superiores, os resultados não podem ser considerados confiáveis.
