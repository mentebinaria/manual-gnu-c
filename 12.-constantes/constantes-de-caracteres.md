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

# Constantes de Caracteres

Uma constante de caractere é escrita com aspas simples, como em `'c'`. No caso mais simples, `c` é um único caractere ASCII que a constante deve representar. A constante tem o tipo `int`, e seu valor é o código do caractere correspondente. Por exemplo, `'a'` representa o código do caractere para a letra ‘a’: 97, no caso.

Para colocar o caractere ‘'’ (aspas simples) na constante de caractere, use a barra invertida (‘\’) como escape. Essa constante de caractere fica assim: `'\''`. A barra invertida aqui funciona como um caractere de escape, e tal sequência, começando com ‘\’, é chamada de sequência de escape.

Para colocar o caractere ‘\’ (barra invertida) na constante de caractere, use outra barra invertida como escape. Essa constante de caractere fica assim: `'\\'`.

Aqui estão todas as sequências de escape que representam caracteres específicos em uma constante de caractere. Os valores numéricos mostrados são os códigos ASCII correspondentes, como números decimais:

```c
'\a' ⇒ 7       /* alarme, CTRL-g */
'\b' ⇒ 8       /* backspace, BS, CTRL-h */
'\t' ⇒ 9       /* tabulação, TAB, CTRL-i */
'\n' ⇒ 10      /* nova linha, CTRL-j */
'\v' ⇒ 11      /* tabulação vertical, CTRL-k */
'\f' ⇒ 12      /* avanço de formulário, CTRL-l */
'\r' ⇒ 13      /* retorno de carro, RET, CTRL-m */
'\e' ⇒ 27      /* caractere de escape, ESC, CTRL-[ */
'\\' ⇒ 92      /* caractere de barra invertida, \ */
'\'' ⇒ 39      /* caractere de aspas simples, ' */
'\"' ⇒ 34      /* caractere de aspas duplas, " */
'\?' ⇒ 63      /* ponto de interrogação, ? */
```

‘\e’ é uma extensão do GNU C; para seguir o padrão C, escreva ‘\33’. (O número após a barra invertida é octal.) Para especificar uma constante de caractere usando decimal, use um cast; por exemplo, `(unsigned char) 27`.

Você também pode escrever códigos de caracteres em octal e hexadecimal como ‘\octalcode’ ou ‘\xhexcode’. Decimal não é uma opção aqui, então códigos octais não precisam começar com ‘0’.

O valor da constante de caractere tem o tipo `int`. No entanto, o código do caractere é tratado inicialmente como um valor do tipo `char`, que é então convertido para `int`. Se o código do caractere for maior que 127 (0177 em octal), o `int` resultante pode ser negativo em uma plataforma onde o tipo `char` tem 8 bits e é com sinal.
