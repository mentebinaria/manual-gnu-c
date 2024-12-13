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

# Designadores de Tipos

Algumas construções em C exigem uma forma de designar um tipo de dado específico, independente de qualquer variável ou expressão que tenha esse tipo. Isso é feito com um **designador de tipo**. Construções que precisam de um designador incluem _casts_ (veja [_Conversão de Tipo Explícita_](#user-content-fn-1)[^1]) e `sizeof` (veja [_Tamanho do Tipo_](#user-content-fn-2)[^2]).

Também usamos designadores de tipos para nos referirmos ao tipo de um valor em C, então você verá muitos designadores de tipo neste manual. Quando dizemos, "O valor tem tipo `int`," `int` é um designador de tipo.

Para criar o designador de qualquer tipo, imagine uma declaração de variável para uma variável desse tipo e exclua o nome da variável e o ponto e vírgula final.

Por exemplo, para designar o tipo de inteiros de palavra completa, começamos com a declaração de uma variável `foo` com esse tipo:

```c
int foo;
```

Então, excluímos o nome da variável `foo` e o ponto e vírgula, deixando apenas `int`. Portanto, o designador de tipo para este tipo é `int`.

E quanto a inteiros longos sem sinal? A partir da declaração:

```c
unsigned long int foo;
```

determinamos que o designador é `unsigned long int`.

Seguindo este procedimento, o designador para qualquer tipo primitivo é simplesmente o conjunto de palavras-chave que especifica esse tipo em uma declaração. O mesmo é válido para tipos compostos como estruturas, uniões e enumerações.

Os designadores para tipos de ponteiros seguem a regra de excluir o nome da variável e o ponto e vírgula, mas o resultado não é tão simples. Veja [_Designadores de Tipos de Ponteiro_](#user-content-fn-3)[^3], como parte do capítulo sobre ponteiros. Veja [_Designadores de Tipos de Arrays_](#user-content-fn-4)[^4], para designadores de tipos de arrays.

Para entender que tipo um designador representa, imagine um nome de variável inserido no lugar certo no designador para fazer uma declaração válida. Qual seria o tipo com o qual essa variável teria sido declarada? Esse é o tipo que o designador designa.

[^1]: Pendente de tradução

[^2]: Pendente de tradução

[^3]: Pendente de tradução

[^4]: Pendente de tradução
