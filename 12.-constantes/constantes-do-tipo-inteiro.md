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

# Constantes do Tipo Inteiro

Uma constante do tipo inteiro consiste em um número que especifica o valor, seguido opcionalmente por sufixos para especificar o tipo de dado.

As constantes mais simples do tipo inteiro são números escritos na base 10 (decimal), como 5, 77 e 403. Uma constante decimal não pode começar com o caractere ‘0’ (zero), pois isso a tornaria uma constante octal.

Você pode obter o efeito de uma constante do tipo inteiro negativa colocando um sinal de menos no início. Em termos gramaticais, isso é uma expressão aritmética, e não uma constante, mas se comporta como uma constante verdadeira.

As constantes do tipo inteiro também podem ser escritas em octal (base 8), hexadecimal (base 16) ou binário (base 2).

* Uma constante **octal** começa com o caractere ‘0’ (zero), seguido por qualquer número de dígitos octais (‘0’ a ‘7’):

```c
0      // zero
077    // 63
0403   // 259
```

Tecnicamente, a constante `0` é uma constante octal, mas podemos considerá-la decimal, pois o valor é o mesmo.

* Uma constante **hexadecimal** começa com ‘0x’ (maiúsculo ou minúsculo), seguido por dígitos hexadecimais (‘0’ a ‘9’, assim como ‘a’ até ‘f’ em maiúsculo ou minúsculo):

```c
0xff   // 255
0XA0   // 160
0xffFF // 65535
```

* Uma constante **binária** começa com ‘0b’ (maiúsculo ou minúsculo), seguida por bits (cada um representado pelos caracteres ‘0’ ou ‘1’):

```c
0b101  // 5
```

As constantes binárias são uma extensão do GNU C e não fazem parte do padrão C.

{% hint style="info" %}
A partir do C23, as constantes binárias fazem parte do padrão.
{% endhint %}

Às vezes, é necessário um espaço após uma constante do tipo inteiro para evitar confusão léxica com os tokens seguintes. Veja _Números Inválidos_.
