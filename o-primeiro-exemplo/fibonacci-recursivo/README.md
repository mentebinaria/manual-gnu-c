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

# Fibonacci Recursiva

Para introduzir os conceitos mais básicos de C, vamos ver um código que implementa uma função matemática simples que faz cálculos com números inteiros. Esta função calcula o enésimo número na série de Fibonnaci, na qual cada número é a soma dos dois números anteriores: 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, ….

```c
int
fib (int n)
{
  if (n <= 2)  /* Isto evita recursividade infinita. */
    return 1;
  else
    return fib (n - 1) + fib (n - 2);
}
```

Este simples programa ilustra vários recursos da linguagem C:

* A definição de uma função cujas primeiras duas linhas constituem no cabeçalho da função. Veja Definição de Funções.
* Um parâmetro de função `n`, referenciado com a variável `n` dentro do corpo da função. Veja Variáveis de Parâmetros de Função. Uma definição de função usa parâmetros para se referir aos valores dos argumentos passados para ela numa chamada de função.
* Aritmética. Programas em C somam com `+` e subtraem com `-`. Veja Aritmética.
* Comparações numéricas. O operador `<=` testa se é "menor ou igual". Veja Comparações Numéricas.
* Constantes inteiras escritas na base 10. Veja Constantes Inteiras.
* Uma chamada de função. A chamada de função `fib (n - 1)` chama a função `fib` passando o valor `n - 1` como seu argumento. Veja Chamadas de Função.
* Um comentário que começa com `/*` e termina com `*/`. O comentário não tem nenhum efeito na execução do programa. Seu propósito é prover explicações para pessoas lendo o código-fonte. Incluir comentários no código é tremendamente importante - eles adicionam contexto de forma que outras pessoas possam entender o código mais rapidamente. Veja Comentários.
* Dois tipos de comandos, o `return` and o `if...else`. Veja Comandos.
* Recursão. A função `fib` chama a si mesma; isto é chamado de _chamada recursiva_. Isto é válido em C e bastante comum.

A função `fib` não seria útil se ela não retornasse. Portanto, funções recursivas, para serem úteis, precisam evitar _recursão infinita_.

Esta definição de função previne a recursão infinita ao tratar o caso especial onde `n` é dois ou menos. Portanto a máxima profundeza de chamadas recursivas é menor que `n`.

* Cabeçalho da Função O nome da função e como ela é chamada.
* Corpo da Função Declarações que implementam a função.

