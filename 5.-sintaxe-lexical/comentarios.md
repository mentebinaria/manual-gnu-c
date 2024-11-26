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

# Comentários

Um comentário encapsula texto que não tem efeito na execução ou no significado do programa.

O propósito dos comentários é explicar o código para as pessoas que o leem. Escrever bons comentários para seu código é extremamente importante – eles devem fornecer informações sobre o contexto, que ajudem os programadores a entender as razões pelas quais o código foi escrito da maneira que está. Você, retornando ao código seis meses depois, precisará da ajuda desses comentários para lembrar por que o escreveu dessa forma.

Comentários desatualizados que se tornam incorretos são contraproducentes, então parte da responsabilidade do desenvolvedor de software é atualizar os comentários conforme necessário para corresponder às mudanças no código do programa.

C permite dois tipos de sintaxe de comentário, o estilo tradicional e o estilo C++. Um comentário tradicional em C começa com '/\*' e termina com '\*/'. Por exemplo,

```c
/* Este é um comentário na sintaxe C tradicional. */
```

Um comentário tradicional pode conter '/\*', mas esses delimitadores não se aninham como pares. O primeiro '/\*' termina o comentário independentemente de ele conter sequências '/\*' ou não.

```c
/* Isto /* é um comentário */ Mas isso não! */
```

Um comentário de linha começa com '//' e termina no final da linha. Por exemplo,

```c
// Isto é um comentário no estilo C++
```

Comentários de linha se aninham, na prática, porque o '//' dentro de um comentário de linha é parte desse comentário:

```c
// a linha inteira é // um comentário
Isto é código, não comentário.
```

É seguro colocar comentários de linha dentro de comentários de bloco, ou vice-versa.

```c
/* comentário tradicional
   // contém comentário de linha
   mais um comentário tradicional
 */ o texto aqui não é um comentário

// comentário de linha /* que contém um comentário tradicional */

```

Mas tenha cuidado ao comentar uma extremidade de um comentário tradicional com um comentário de linha. O delimitador '/\*' não inicia um comentário se ocorrer dentro de um comentário já iniciado.

```c
 // comentário de linha  /* e aqui normalmente começaria um comentário de bloco
    Oops! O comentário de linha acabou;
    isto não é mais um comentário.  */
```

Comentários não são reconhecidos dentro de strings constantes. `"/* blah */"` é a string constante ‘`/* blah */`’, não uma string vazia.

Um comentário é sintaticamente equivalente ao espaço em branco, então ele sempre separa tokens. Assim,

```c
  int/* comment */foo;
```

é equivalente a

```c
  int foo;
```

mas um código limpo sempre usa espaço em branco real para separar o comentário visualmente do código ao redor.
