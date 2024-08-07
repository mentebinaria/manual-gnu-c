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

# Identificadores

Um _identificador_ (nome) em C é uma sequência de letras, dígitos ou '\_' (caractere de sublinha ou _underscore_), que não começa com um dígito. A maioria dos compiladores também permite '$'. Um identificador pode ter o comprimento que você desejar; por exemplo,

```c
int anti_dis_establishment_arian_ism;
```

Letras em identificadores são sensíveis a maiúsculas e minúsculas em C; assim, `a` e `A` são dois identificadores diferentes.

Identificadores em C são usados como nomes de variáveis, nomes de funções, nomes de `typedef`, constantes de enumeração, tags de tipo, nomes de campo e rótulos. Certos identificadores em C são palavras-chave, o que significa que têm significados sintáticos específicos. Palavras-chave em C são palavras reservadas, o que significa que você não pode usá-las de outra forma. Por exemplo, você não pode definir uma variável ou função chamada `return` ou `if`.

Você também pode incluir outros caracteres, até mesmo caracteres não ASCII, em identificadores escrevendo seus nomes de caracteres Unicode, que começam com '\u' ou '\U', no nome do identificador. Veja [Códigos de Caracteres Unicode](#user-content-fn-1)[^1]. No entanto, geralmente é uma má ideia usar caracteres não ASCII em identificadores, e quando os nomes são escritos em inglês, nunca precisam de caracteres não ASCII. Veja [Escreva Programas em Inglês!](escreva-programas-em-ingles.md).

Como mencionado acima, é necessário (pelo menos um) espaço em branco para separar dois identificadores consecutivos ou para separar um identificador de uma constante numérica anterior ou seguinte.

[^1]: Capítulo pendente de tradução
