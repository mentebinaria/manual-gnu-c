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

# Tipos de Dados de Ponto Flutuante

Ponto flutuante é o análogo binário da notação científica: internamente, representa um número como uma fração e um expoente binário; o valor é essa fração multiplicada pela potência de 2 especificada. (O padrão C nominalmente permite outras bases, mas no GNU C a base é sempre 2.)

Por exemplo, para representar o número 6, a fração seria 0,75 e o expoente seria 3; juntos representam o valor `0,75 * 2^3`, ou seja, `0,75 * 8`. O valor 1,5 usaria 0,75 como fração e 1 como expoente. O valor 0,75 usaria 0,75 como fração e 0 como expoente. O valor 0,375 usaria 0,75 como fração e -1 como expoente.

Esses expoentes binários são usados por instruções da máquina. Você pode escrever uma constante de ponto flutuante dessa forma, usando hexadecimal, se desejar; mas normalmente escrevemos números de ponto flutuante em decimal (base 10). Veja [_Constantes de Ponto Flutuante_](#user-content-fn-1)[^1].

C tem três tipos de dados de ponto flutuante:

**`double`**\
Ponto flutuante de "dupla precisão", que usa 64 bits. Este é o tipo de ponto flutuante normal, e computadores modernos geralmente fazem seus cálculos de ponto flutuante nesse tipo ou em algum tipo mais amplo. Exceto quando há um motivo especial para fazer diferente, este é o tipo a ser usado para valores de ponto flutuante.

**`float`**\
Ponto flutuante de "precisão simples", que usa 32 bits. É útil para valores de ponto flutuante armazenados em estruturas e arrays, para economizar espaço quando a precisão total de `double` não é necessária. Além disso, a aritmética de precisão simples é mais rápida em alguns computadores, o que pode ser útil ocasionalmente. Mas não com frequência — a maioria dos programas não usa o tipo `float`.

Seria mais claro se `float` fosse o nome do tipo que usamos para a maioria dos valores de ponto flutuante; no entanto, por razões históricas, não é assim.

**`long double`**\
Ponto flutuante de "precisão estendida", com precisão de 80 bits ou 128 bits, dependendo da máquina em uso. Em algumas máquinas, que não possuem formato de ponto flutuante mais amplo do que `double`, este é equivalente a `double`.

A aritmética de ponto flutuante levanta muitas questões sutis. Veja [_Ponto Flutuante em Profundidade_](#user-content-fn-2)[^2] para mais informações.

[^1]: 

[^2]: Pendente de tradução
