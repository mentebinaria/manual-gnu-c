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

# Constantes de Números Imaginários

Um número complexo consiste em uma parte real mais uma parte imaginária. (Você pode omitir uma das partes se ela for zero.) Esta seção explica como escrever constantes numéricas com valores imaginários. Ao adicionar essas constantes a constantes numéricas de valor real ordinário, podemos criar constantes com valores complexos.

A forma simples de escrever uma constante numérica imaginária é anexar o sufixo ‘i’ ou ‘I’, ou ‘j’ ou ‘J’, a uma constante inteira ou de ponto flutuante. Por exemplo, `2.5fi` tem o tipo `_Complex float` e `3i` tem o tipo `_Complex int`. As quatro letras de sufixo alternativas são todas equivalentes.

A outra maneira de escrever uma constante imaginária é multiplicar uma constante real por `_Complex_I`, que representa o número imaginário `i`. O padrão C não suporta sufixos com ‘i’ ou ‘j’, então este método mais trabalhoso é necessário.

Para escrever uma constante complexa com uma parte real não nula e uma parte imaginária não nula, escreva as duas separadamente e as some, assim:

```c
4.0 + 3.0i
```

Isso dá o valor `4 + 3i`, com o tipo `_Complex double`.

Essa soma pode incluir várias constantes reais, ou nenhuma. Da mesma forma, pode incluir várias constantes imaginárias, ou nenhuma. Por exemplo:

```c
_Complex double foo, bar, quux;

foo = 2.0i + 4.0 + 3.0i; /* A parte imaginária é 5.0. */
bar = 4.0 + 12.0; /* A parte imaginária é 0.0. */
quux = 3.0i + 15.0i; /* A parte real é 0.0. */
```

Veja [_Tipos de Dados Complexos_](../11.-tipos-primitivos/tipos-de-dados-complexos.md).
