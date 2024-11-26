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

# Operadores e Pontuação

Aqui descrevemos a sintaxe lexical de operadores e de pontuação em C. Os operadores específicos de C e seus significados são apresentados em capítulos subsequentes.

A maioria dos operadores em C consiste em um ou dois caracteres que não podem ser usados em identificadores. Os caracteres usados para operadores em C são ‘!\~^&|\*/%+-=<>,.?:’.

Alguns operadores são de um único caractere. Por exemplo, ‘-’ é o operador de negação (com um operando) e o operador de subtração (com dois operandos).

Alguns operadores são de dois caracteres. Por exemplo, ‘++’ é o operador de incremento. O reconhecimento de operadores de múltiplos caracteres funciona agrupando tantos caracteres consecutivos quanto possível para constituir um operador.

Por exemplo, a sequência de caracteres ‘++’ é sempre interpretada como o operador de incremento; portanto, se quisermos escrever duas instâncias consecutivas do operador ‘+’, devemos separá-las com um espaço para que não se combinem como um único token. Aplicando a mesma regra, `a+++++b` é sempre tokenizado como `a++ ++ + b`, e não como `a++ + ++b`, mesmo que a última forma pudesse fazer parte de um programa C válido, e a primeira não (já que `a++` não é um lvalue e, portanto, não pode ser o operando de `++`).

Alguns operadores de C são palavras-chave em vez de caracteres especiais. Eles incluem `sizeof` (veja [Tamanho de Tipos](#user-content-fn-1)[^1]) e `_Alignof` (veja [Alinhamento de Tipos](#user-content-fn-2)[^2]).

Os caracteres ‘;{}’ são usados para pontuação e agrupamento. O ponto e vírgula (‘;’) termina uma declaração. As chaves (‘{’ e ‘}’) iniciam e terminam um bloco no nível da declaração (veja Blocos[^3]), e cercam o inicializador (veja Inicializadores[^4]) para uma variável com múltiplos elementos ou campos (como arrays ou structs).

Colchetes (‘\[’ e ‘]’) são usados para indexação de arrays, como em `array[5]`.

Parênteses são usados em expressões para o aninhamento explícito de expressões (veja [Aritmética Básica](#user-content-fn-5)[^5]), ao redor das declarações de parâmetros em uma declaração ou definição de função, e ao redor dos argumentos em uma chamada de função, como em `printf("Foo %d\n", i)` (veja [Chamadas de Função](#user-content-fn-6)[^6]). Vários tipos de declarações também usam parênteses como parte de sua sintaxe — por exemplo, declarações `if`, declarações `for`, declarações `while` e declarações `switch`. Veja [Declaração if](#user-content-fn-7)[^7] e seções seguintes.

Parênteses também são necessários ao redor do operando das palavras-chave dos operadores `sizeof` e `_Alignof` quando o operando é um tipo de dado em vez de um valor. Veja [Tamanho do Tipo](#user-content-fn-8)[^8].

[^1]: Capítulo pendente de tradução

[^2]: Capítulo pendente de tradução

[^3]: Capítulo pendente de tradução

[^4]: Capítulo pendente de tradução

[^5]: Capítulo pendente de tradução

[^6]: Capítulo pendente de tradução

[^7]: Capítulo pendente de tradução

[^8]: Capítulo pendente de tradução
