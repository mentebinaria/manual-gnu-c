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

# Expressão Condicional

C possui uma expressão condicional que seleciona uma de duas expressões para calcular e obter o valor. Ela se parece com isto:

```c
condição ? se_verdadeiro : se_falso
```

## Regras para o Operador Condicional

O primeiro operando, `condição`, deve ser um valor que possa ser comparado com zero — um número ou um ponteiro. Se for verdadeiro (diferente de zero), a expressão condicional calcula `se_verdadeiro` e seu valor se torna o valor da expressão condicional. Caso contrário, a expressão condicional calcula `se_falso` e seu valor se torna o valor da expressão condicional. A expressão condicional sempre calcula apenas uma das duas, `se_verdadeiro` ou `se_falso`, nunca ambas.

Aqui está um exemplo: o valor absoluto de um número `x` pode ser escrito como:

```c
(x >= 0 ? x : -x)
```

**Aviso:** Os operadores de expressão condicional têm uma precedência sintática relativamente baixa. Exceto quando a expressão condicional é usada como argumento em uma chamada de função, escreva parênteses ao redor dela. Para maior clareza, sempre escreva parênteses ao redor se ela se estender por mais de uma linha.

Os operadores de atribuição e o operador vírgula (veja [Operador Vírgula](operador-virgula.md)) têm precedência mais baixa do que os operadores de expressão condicional, então coloque parênteses ao redor deles quando aparecerem dentro de uma expressão condicional. Veja [Ordem de Execução](#user-content-fn-1)[^1].

## Ramos do Operador Condicional

Chamamos os ramos (_branches_) da expressão condicional de _se\_verdadeiro_ e _se\_falso_.

Os dois ramos normalmente devem ter o mesmo tipo, mas algumas exceções são permitidas. Se ambos forem tipos numéricos, a expressão condicional converte ambos para o tipo comum (veja [Tipo Comum](#user-content-fn-2)[^2]).

Com ponteiros (veja Ponteiros[^3]), os dois valores podem ser ponteiros para tipos minimamente compatíveis (veja [Tipos Compatíveis](#user-content-fn-4)[^4]). Nesse caso, o tipo de resultado é um ponteiro semelhante, cujo tipo de destino combina todos os qualificadores de tipo (veja [Qualificadores de Tipo](#user-content-fn-5)[^5]) de ambos os ramos.

Se um dos ramos tiver o tipo `void *` e o outro for um ponteiro para um objeto (não para uma função), a expressão condicional converte o ramo `void *` para o tipo do outro.

Se um dos ramos for uma constante inteira com valor zero e o outro for um ponteiro, a expressão condicional converte zero para o tipo do ponteiro.

No GNU C, você pode omitir _se\_verdadeiro_ em uma expressão condicional. Nesse caso, se a condição for diferente de zero, seu valor se torna o valor da expressão condicional, após a conversão para o tipo comum. Assim,

```c
x ? : y
```

tem o valor de `x` se for diferente de zero; caso contrário, o valor de `y`.

Omitir _se\_verdadeiro_ é útil quando a condição tem efeitos colaterais. Nesse caso, escrever a expressão duas vezes executaria os efeitos colaterais duas vezes, mas escrevê-la uma vez os executa apenas uma vez. Por exemplo, supondo que a função `next_element` avance uma variável ponteiro para apontar para o próximo elemento em uma lista e retorne o novo ponteiro,

```c
next_element () ? : default_pointer
```

é uma maneira de avançar o ponteiro e usar seu novo valor, se ele não for nulo, mas usar `default_pointer` se for nulo. Não podemos fazer da seguinte forma:

```c
next_element () ? next_element () : default_pointer
```

porque isso avançaria o ponteiro uma segunda vez.

[^1]: Capítulo pendente de tradução

[^2]: Capítulo pendente de tradução

[^3]: Capítulo pendente de tradução

[^4]: Capítulo pendente de tradução

[^5]: Capítulo pendente de tradução
