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

# Continuação de Linha

A sequência formada por uma barra invertida e um caractere de nova linha é completamente ignorada em qualquer lugar em um programa C. Isso torna possível dividir uma única linha de código-fonte em várias linhas no arquivo fonte. O GNU C tolera e ignora outros espaços em branco entre a barra invertida e a nova linha. Em particular, ele sempre ignora um caractere CR (carriage return) ali, caso algum editor de texto decida terminar a linha com a sequência CRLF.

O principal uso da continuação de linha em C é para definições de macro que seriam inconvenientemente longas para uma única linha (veja Macros[^1]).

É possível continuar um comentário de linha em outra linha com a sequência barra invertida-nova linha. Você pode colocar tal sequência no meio de um identificador, até mesmo numa palavra-chave, ou num operador. Você pode até dividir ‘/\*’, ‘\*/’, e ‘//’ em várias linhas com a sequência barra invertida-nova linha. Aqui está um exemplo feio:

```c
/\
*
*/ fo\
o +\
= 1\
0;
```

Isso é equivalente a ‘`/* */ foo += 10;`’.

Não faça essas coisas em programas reais, pois elas tornam o código difícil de ler.

**Nota**: Por questão de uso de certas ferramentas no código-fonte, é sensato terminar cada arquivo fonte com um caractere de nova linha que não seja precedido por uma barra invertida, para que ele realmente termine a última linha.

[^1]: Capítulo pendente de tradução
