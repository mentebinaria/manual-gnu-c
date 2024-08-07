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

# Escreva Programas em Inglês!

Em princípio, você pode escrever os nomes de funções e variáveis em um programa, assim como os comentários, em qualquer idioma. C permite qualquer tipo de caractere Unicode em comentários, e você pode colocá-los em identificadores com um prefixo especial (veja [Códigos de Caracteres Unicode](#user-content-fn-1)[^1]). No entanto, para permitir que programadores de todos os países compreendam e desenvolvam o programa, é melhor, nas circunstâncias atuais, escrever todos os identificadores e comentários em inglês.

O inglês é a língua comum dos programadores; em todos os países, os programadores geralmente aprendem inglês. Se os nomes e comentários em um programa forem escritos em inglês, a maioria dos programadores em Bangladesh, Bélgica, Bolívia, Brasil, Bulgária e Burundi poderá entendê-los. Em todos esses países, a maioria dos programadores fala inglês, ou pelo menos o lê, mas eles não leem os idiomas uns dos outros. Na Índia, com tantos idiomas, dois programadores podem não ter um idioma comum além do inglês.

Se você não se sente confiante em escrever em inglês, faça o melhor que puder e siga cada comentário em inglês com uma versão em um idioma que você escreve melhor; adicione uma nota no comentário pedindo a outros para traduzirem isso para o inglês. Alguém eventualmente fará isso.

A interface do usuário do programa é uma questão diferente. Não precisamos escolher um idioma para isso; é fácil suportar múltiplos idiomas e deixar cada usuário escolher o idioma para exibição do texto. Isso requer escrever o programa para suportar a localização de sua interface. (O pacote `gettext` existe para dar suporte a isso; veja [The GNU C Library](https://www.gnu.org/software/libc/manual/html\_node/Message-Translation.html#Message-Translation) no _The GNU C Library Reference Manual_.) Dessa forma, um esforço de tradução baseado em comunidade pode fornecer suporte para todos os idiomas que os usuários desejam usar.

[^1]: Capítulo pendente de tradução
