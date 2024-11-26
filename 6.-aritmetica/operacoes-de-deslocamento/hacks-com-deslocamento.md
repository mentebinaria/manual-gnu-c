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

# Hacks com Deslocamento

Você pode usar os operadores de deslocamento para diversos hacks (soluções engenhosas) úteis. Por exemplo, dada uma data especificada pelo dia do mês `d`, mês `m` e ano `y`, você pode armazenar toda a data em um único inteiro `date`:

```c
unsigned int d = 12;        /* 12 em binário é 0b1100.  */
unsigned int m = 6;         /* 6 em binário é 0b110.  */
unsigned int y = 1983;      /* 1983 em binário é 0b11110111111.  */
unsigned int date = (((y << 4) + m) << 5) + d;
/* Adiciona 0b11110111111000000000
   e 0b11000000 e 0b1100.
   A soma é 0b11110111111011001100.  */
```

Para extrair o dia, mês e ano de `date`, use uma combinação de deslocamento e resto:

```c
/* 32 em binário é 0b100000.  */
/* O resto da divisão por 32 dá os 5 bits menos significativos, 0b1100.  */
d = date % 32;
/* Deslocar 5 bits para a direita descarta o dia, restando 0b111101111110110.
   O resto da divisão por 16 dá os 4 bits menos significativos restantes, 0b110.  */
m = (date >> 5) % 16;
/* Deslocar 9 bits para a direita descarta dia e mês,
   restando 0b111101111110.  */
y = date >> 9;
```

`-1 << LOWBITS` é uma maneira inteligente de criar um inteiro cujos `LOWBITS` bits menos significativos são todos 0 e o restante são todos 1. `-(1 << LOWBITS)` é equivalente a isso, devido à associatividade da multiplicação, já que negar um valor é equivalente a multiplicá-lo por -1.
