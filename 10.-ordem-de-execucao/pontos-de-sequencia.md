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

# Pontos de Sequência

Existem alguns pontos no código onde C faz garantias limitadas sobre a ordem das operações. Esses pontos são chamados de _pontos de sequência_. Aqui estão os casos em que eles ocorrem:

* **No final de uma&#x20;**_**expressão completa**_: ou seja, uma expressão que não faz parte de uma expressão maior. Todos os efeitos colaterais gerados por essa expressão são realizados antes que a execução passe para o código subsequente.
*   **No final do primeiro operando de certos operadores**: `,`, `&&`, `||` e `?:`. Todos os efeitos colaterais especificados por esse operando são realizados antes de qualquer execução do próximo operando.

    \
    As vírgulas que separam argumentos em uma chamada de função **não são operadores vírgula** e não criam pontos de sequência. A regra para argumentos de função e a regra para operandos são diferentes (veja [_Ordenação de Operandos_](ordenacao-de-operandos.md)).
*   **Logo antes de chamar uma função**: todos os efeitos colaterais gerados pelas expressões dos argumentos são realizados antes de chamar a função.

    Se a função a ser chamada não for constante — isto é, se for computada por uma expressão — todos os efeitos colaterais nessa expressão são realizados antes de chamar a função.

A ordenação imposta por um ponto de sequência se aplica localmente a um intervalo limitado de código, conforme indicado em cada caso acima. Por exemplo, a ordenação imposta pelo operador vírgula não se aplica ao código fora dos operandos desse operador. Assim, neste código:

```c
(x = 5, foo (x)) + x * x
```

o ponto de sequência do operador vírgula ordena `x = 5` antes de `foo (x)`, mas `x * x` pode ser calculado antes ou depois deles.
