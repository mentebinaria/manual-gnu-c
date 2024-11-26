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

# Divisão e Resto

A divisão de inteiros em C arredonda o resultado para um número inteiro. O resultado é sempre arredondado em direção a zero.

```c
 16 / 3  ⇒ 5
-16 / 3  ⇒ -5
 16 / -3 ⇒ -5
-16 / -3 ⇒ 5
```

Para obter o resto correspondente, use o operador ‘%’:

```c
 16 % 3  ⇒ 1
-16 % 3  ⇒ -1
 16 % -3 ⇒ 1
-16 % -3 ⇒ -1
```

‘%’ tem a mesma precedência de operador que ‘/’ e ‘\*’.

A partir do quociente arredondado e do resto, você pode reconstruir o dividendo, assim:

```c
int
original_dividend (int divisor, int quotient, int remainder)
{
  return divisor * quotient + remainder;
}
```

Para fazer uma divisão não arredondada, use ponto flutuante. Se apenas um operando for de ponto flutuante, ‘/’ converte o outro operando para ponto flutuante.

```c
16.0 / 3   ⇒ 5.333333333333333
16   / 3.0 ⇒ 5.333333333333333
16.0 / 3.0 ⇒ 5.333333333333333
16   / 3   ⇒ 5
```

O operador de resto ‘%’ não é permitido para operandos de ponto flutuante, porque não é necessário. O conceito de resto faz sentido para inteiros porque o resultado da divisão de inteiros deve ser um número inteiro. Para ponto flutuante, o resultado da divisão é um número de ponto flutuante, ou seja, uma fração, que diferirá do resultado exato apenas por uma quantidade muito pequena.

Existem funções na biblioteca padrão C para calcular restos a partir da divisão de números de ponto flutuante por valores inteiros. Veja [The GNU C Library](https://www.gnu.org/software/libc/manual/html\_mono/libc.html#Remainder-Functions) no _The GNU C Library Reference Manual_ (disponível somente em inglês).

A divisão de inteiros causa estouro em um caso específico: dividir o menor valor negativo para o tipo de dado (veja [Valores Máximos e Mínimos](#user-content-fn-1)[^1]) por -1. Isso ocorre porque o resultado correto, que é o número positivo correspondente, não cabe (veja [Estouro de Inteiros](estouro-de-inteiros/)) no mesmo número de bits. Em alguns computadores atualmente em uso, isso sempre causa um sinal SIGFPE (veja Sinais[^2]), o mesmo comportamento que a opção -ftrapv especifica (veja [Estouro de Inteiros com Sinal](estouro-de-inteiros/estouro-de-inteiros-com-sinal.md)).

A divisão por zero leva a resultados imprevisíveis—dependendo do tipo de computador, pode causar um sinal SIGFPE ou pode produzir um resultado numérico.

**Atenção**: Certifique-se de que o programa não divide por zero. Se você não puder garantir que o divisor não é zero, teste se ele é zero e pule a divisão, se for o caso.

[^1]: Capítulo pendente de tradução

[^2]: Capítulo pendente de tradução
