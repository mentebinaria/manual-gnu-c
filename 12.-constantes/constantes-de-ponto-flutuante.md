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

# Constantes de Ponto Flutuante

Uma constante de ponto flutuante deve ter um ponto decimal, um expoente de dez, ou ambos; isso a distingue de uma constante do tipo inteiro.

Para indicar um expoente, use ‘e’ ou ‘E’. O valor do expoente segue em seguida, sempre como um número decimal; ele pode opcionalmente começar com um sinal. O expoente `n` significa multiplicar o valor da constante por dez elevado à potência `n`.

Assim, ‘1500.0’, ‘15e2’, ‘15e+2’, ‘15.0e2’, ‘1.5e+3’, ‘.15e4’ e ‘15000e-1’ são seis maneiras de escrever um número de ponto flutuante cujo valor é 1500. Todas são equivalentes em princípio.

**Exemplos com Pontos Decimais:**

```c
1.0
1000.
3.14159
.05
.0005
```

**Constantes Equivalentes com Expoentes:**

```c
1e0, 1.0000e0
100e1, 100e+1, 100E+1, 1e3, 10000e-1
3.14159e0
5e-2, .0005e+2, 5E-2, .0005E2
.05e-2
```

Uma constante de ponto flutuante normalmente tem o tipo `double`. Você pode forçá-la a ser do tipo `float` adicionando ‘f’ ou ‘F’ no final. Por exemplo:

```c
3.14159f
3.14159e0f
1000.f
100E1F
.0005f
.05e-2f
```

Da mesma forma, adicionar ‘l’ ou ‘L’ no final força a constante a ser do tipo `long double`.

Você também pode usar expoentes em constantes de ponto flutuante em hexadecimal, mas como ‘e’ seria interpretado como um dígito hexadecimal, o caractere ‘p’ ou ‘P’ (de "potência") indica um expoente.

O expoente em uma constante de ponto flutuante hexadecimal é um inteiro decimal com sinal opcional que especifica uma potência de 2 (não 10 ou 16) a ser multiplicada no número.

**Exemplos:**

```c
0xAp2        // 40 em decimal
0xAp-1       // 5 em decimal
0x2.0Bp4     // 32.6875 em decimal
0xE.2p3      // 113 em decimal
0x123.ABCp0  // 291.6708984375 em decimal
0x123.ABCp4  // 4666.734375 em decimal
0x100p-8     // 1
0x10p-4      // 1
0x1p+4       // 16
0x1p+8       // 256
```

Veja [_Tipos de Dados de Ponto Flutuante_](../11.-tipos-primitivos/tipos-de-dados-de-ponto-flutuante.md).
