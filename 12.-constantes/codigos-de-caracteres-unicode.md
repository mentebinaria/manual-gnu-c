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

# Códigos de Caracteres Unicode

Você pode especificar caracteres Unicode, para constantes do tipo caractere individuais ou como parte de constantes do tipo string (veja [_Constantes do Tipo String_](constantes-do-tipo-string.md)), usando sequências de escape; e até mesmo em identificadores C. Use a sequência de escape ‘\u’ com um código Unicode hexadecimal de 16 bits. Se o valor do código for grande demais para 16 bits, use a sequência de escape ‘\U’ com um código Unicode hexadecimal de 32 bits. (Esses códigos são chamados de nomes universais de caracteres.) Por exemplo:

```c
\u6C34      /* Código de 16 bits (UTF-16) */
\U0010ABCD  /* Código de 32 bits (UTF-32) */
```

Uma forma de utilizá-los é em constantes do tipo string UTF-8 (veja [_Constantes do Tipo String UTF-8_](constantes-do-tipo-string-utf-8.md)). Por exemplo:

```c
u8"fóó \u6C34 \U0010ABCD"
```

Você também pode usá-los em constantes do tipo caractere largo (veja _Constantes do Tipo Caractere Largo_), como neste exemplo:

```c
u'\u6C34'      /* Código de 16 bits */
U'\U0010ABCD'  /* Código de 32 bits */
```

E em constantes do tipo string larga (veja _Constantes do Tipo String Larga_), como neste exemplo:

```c
u"\u6C34\u6C33"  /* Código de 16 bits */
U"\U0010ABCD"    /* Código de 32 bits */
```

Além disso, você pode usar esses códigos em um identificador:

```c
int foo\u6C34bar = 0;
```

Os códigos no intervalo de D800 a DFFF não são válidos em Unicode. Códigos menores que 00A0 também são proibidos, exceto pelos códigos 0024, 0040 e 0060; esses caracteres são, na verdade, caracteres de controle ASCII, que você pode especificar com outras sequências de escape (veja [_Constantes de Caracteres_](constantes-de-caracteres.md)).
