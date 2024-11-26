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

# Caracteres

Arquivos de código-fonte em GNU C são geralmente escritos utilizando-se o conjunto de caracteres [ASCII](https://pt.wikipedia.org/wiki/ASCII), que foi definido na década de 1960 para o inglês. No entanto, eles também podem incluir caracteres Unicode representados na codificação de múltiplos bytes [UTF-8](https://pt.wikipedia.org/wiki/UTF-8). Isso possibilita a representação de letras acentuadas como ‘á’, assim como outros scripts, tais como árabe, chinês, cirílico, hebraico, japonês e coreano.

No código fonte C, caracteres não ASCII são válidos em comentários, em constantes de caracteres largos (veja [Constantes de Caracteres Largos](#user-content-fn-1)[^1]) e em strings constantes (veja [Strings Constantes](#user-content-fn-2)[^2]).

Outra maneira de especificar caracteres não ASCII em constantes (caracteres ou strings) e identificadores é com uma sequência de escape começando com barra invertida, especificando o caractere Unicode pretendido. (Veja [Códigos de Caracteres Unicode](#user-content-fn-3)[^3].) Isso especifica caracteres não ASCII sem colocar um caractere não ASCII real no próprio arquivo de código-fonte.

C também  aceita pares de caracteres chamados dígrafos para certos caracteres. Veja Dígrafos[^4].

{% hint style="warning" %}
Em alguns sistemas obscuros, GNU C utiliza UTF-EBCDIC ao invés de UTF-8, mas não vale a pena explicar isso neste manual.
{% endhint %}

[^1]: Capítulo pendente de tradução

[^2]: Capítulo pendente de tradução

[^3]: Capítulo pendente de tradução

[^4]: Capítulo pendente de tradução
