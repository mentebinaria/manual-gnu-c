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

# Aritmética de Inteiros

Cada uma das operações aritméticas básicas em C tem duas variantes para inteiros: com e sem sinal. A escolha é determinada pelos tipos de dados de seus operandos.

Cada tipo de dado inteiro em C é ou _signed_ (com sinal) ou _unsigned_ (sem sinal). Um tipo com sinal pode conter um intervalo de números positivos e negativos, com o zero próximo ao meio do intervalo. Um tipo sem sinal pode conter apenas números não negativos; seu intervalo começa em zero e vai para cima.

Os tipos inteiros mais básicos são  `int`, que normalmente pode conter números de -2.147.483.648 a 2.147.483.647, e o `unsigned int`, que normalmente pode conter números de 0 a 4.294.967.295. (Isso assume que `int` tem 32 bits de largura, o que é sempre verdadeiro para GNU C em computadores reais, mas nem sempre em controladores embarcados.) Veja [Tipos Inteiros](#user-content-fn-1)[^1], para informações completas sobre tipos inteiros.

Quando uma operação aritmética básica recebe dois operandos com sinal, ela realiza aritmética com sinal. Quando recebe dois operandos sem sinal, realiza aritmética sem sinal.

Se um operando for `unsigned int` e o outro `int`, o operador trata ambos como sem sinal. De maneira mais geral, o tipo comum dos operandos determina se a operação é sinalizada ou não. [Veja Tipo Comum](#user-content-fn-2)[^2].

Imprimir os resultados de uma aritmética sem sinal com `printf` usando ‘%d’ pode produzir resultados surpreendentes para valores distantes de zero. Mesmo que as regras acima digam que a computação foi feita com aritmética sem sinal, o resultado impresso na tela pode parecer com sinal!

A explicação é que o padrão de bits resultante de uma adição, subtração ou multiplicação é, na verdade, o mesmo para operações com e sem sinal. A diferença está apenas no tipo de dado do resultado, que afeta a interpretação do padrão de bits resultante e se a operação aritmética pode ou não causar um estouro (veja a próxima seção).

Mas ‘%d’ não sabe o tipo de dado de seu argumento. Ele vê apenas o padrão de bits do valor e está definido para interpretá-lo como `signed int`. Para imprimi-lo como sem sinal, é necessário usar ‘%u’ em vez de ‘%d’. Veja [The GNU C Library](https://www.gnu.org/software/libc/manual/html\_mono/libc.html#Formatted-Output) no _The GNU C Library Reference Manual_ (disponível somente em inglês).

A aritmética em C nunca opera diretamente em tipos inteiros estreitos (aqueles com menos bits que `int`; veja [Inteiros Estreitos](#user-content-fn-3)[^3]). Em vez disso, ela os "promove" para `int`. Veja [Promoções de Operando](#user-content-fn-4)[^4].



[^1]: 



[^2]: Capítulo pendente de tradução

[^3]: Capítulo pendente de tradução

[^4]: Capítulo pendente de tradução
