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

# Conversão entre Tipos Inteiros

C converte tipos inteiros implicitamente em muitas situações. Os tipos inteiros estreitos, como `char` e `short`, são convertidos para `int` sempre que usados em operações aritméticas. A atribuição de um novo valor a uma variável inteira (ou outro _lvalue_) converte o valor para o tipo da variável.

Você também pode converter explicitamente um tipo inteiro para outro usando um operador de cast. Veja [_Conversão de Tipo Explícita_](#user-content-fn-1)[^1].

O processo de conversão para um tipo mais largo é direto: o valor permanece inalterado. A única exceção ocorre ao converter um valor negativo (obviamente em um tipo com sinal) para um tipo sem sinal mais largo. Nesse caso, o resultado é um valor positivo com os mesmos bits (veja [_Inteiros em Profundidade_](#user-content-fn-2)[^2]).

A conversão para um tipo mais estreito, também chamada de **truncamento**, envolve descartar alguns bits do valor. Isso não é considerado estouro (veja [_Estouro de Inteiros_](../../6.-aritmetica/estouro-de-inteiros/)), pois a perda de bits significativos é uma consequência normal do truncamento. O mesmo se aplica à conversão entre tipos com e sem sinal da mesma largura.

Mais informações sobre conversões em atribuições estão em [_Conversões de Tipo em Atribuições_](#user-content-fn-3)[^3]. Para conversões em operações aritméticas, veja [_Promoção de Argumentos_](#user-content-fn-4)[^4].

[^1]: 

[^2]: Pendente de tradução

[^3]: 

[^4]: Pendente de tradução
