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

# Operadores Lógicos

Os _operadores lógicos_ combinam valores verdade (verdadeiro ou falso), que normalmente são representados em C como números. Qualquer expressão com um valor numérico é um valor verdade válido: zero significa falso, e qualquer outro valor significa verdadeiro. Um tipo de ponteiro também é significativo como valor verdade; um ponteiro nulo (que é zero) significa falso, e um ponteiro não nulo significa verdadeiro (veja [Tipos de Ponteiro](#user-content-fn-1)[^1]). O valor de um operador lógico é sempre 1 ou 0 e tem o tipo `int` (veja [Tipos Inteiros](#user-content-fn-2)[^2]).

Os operadores lógicos são usados principalmente na condição de uma instrução `if`, ou no teste final de uma instrução `for` ou `while` (veja Instruções[^3]). No entanto, eles são válidos em qualquer contexto onde uma expressão com valor inteiro seja permitida.

```c
! exp
```

Operador unário para "não" lógico. O valor é 1 (verdadeiro) se `exp` for 0 (falso), e 0 (falso) se `exp` for diferente de zero (verdadeiro).

**Aviso:** se `exp` for qualquer coisa além de um _lvalue_ ou uma chamada de função, você deve escrever parênteses ao redor dela.

```c
left && right
```

O operador binário "e" lógico computa `left` e, se necessário, `right`. Se ambos os operandos forem verdadeiros, a expressão `&&` retorna o valor 1 (verdadeiro). Caso contrário, a expressão `&&` retorna o valor 0 (falso). Se `left` resultar em um valor falso, isso determina o resultado geral, então `right` nem é computado.

```c
left || right
```

O operador binário "ou" lógico computa `left` e, se necessário, `right`. Se pelo menos um dos operandos for verdadeiro, a expressão `||` retorna o valor 1 (verdadeiro). Caso contrário, a expressão `||` retorna o valor 0 (falso). Se `left` resultar em um valor verdadeiro, isso determina o resultado geral, então `right` nem é computado.

**Aviso:** nunca confie na precedência relativa de `&&` e `||`. Quando você usá-los juntos, sempre use parênteses para especificar explicitamente como eles se aninham, como mostrado aqui:

```c
if ((r != 0 && x % r == 0)
    ||
    (s != 0 && x % s == 0))
```

[^1]: Capítulo pendente de tradução

[^2]: Capítulo pendente de tradução

[^3]: Capítulo pendente de tradução
