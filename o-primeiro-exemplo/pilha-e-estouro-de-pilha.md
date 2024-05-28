---
description: The Stack, And Stack Overflow
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

# Pilha e Estouro de Pilha

Recursão tem uma desvantagem: há um limite no número de níveis aninhados de chamadas de função que um programa pode fazer. Em C, cada chamada de função aloca um bloco de memória que é utilizado até que a chamada retorne. A linguagem C aloca estes blocos consecutivamente numa grande área de memória conhecida como _pilha (stack)_, portanto chamamos este blocos de _quadros de pilha (stack frames)_.

O tamanho da pilha é limitado; se um programa tenta usar muito dela, isso causa uma falha porque a pilha estará cheia. Isso é chamado de _estouro de pilha (stack overflow)_.

Estouros de pilha no GNU/Linux se manifestam tipicamente como o _sinal_ chamado de `SIGSEGV`, também conhecido como "falha de segmentação" ("segmentation fault"). Por padrão, este sinal encerra a execução do programa imediatamente ao invés de permitir que o programa se recupere ou atinja seu fim esperado. (Nestes casos, nós normalmente falamos que o programa "crashou"). Veja Sinais.

{% hint style="info" %}
Aqui me rendi ao neologismo "crashou", oriundo do inglês "crash". Até pensei em usar "travou", mas este termo nós brasileiros normalmente utilizamos quando o programa para de responder ("congela"), mas numa situação de estouro de pilha, o programa é encerrado e não fica "congelado" ou "travado".
{% endhint %}

Não é conveniente tentar observar um estouro de pilha passando um número grande como argumento para uma função recursiva que implemente Fibonacci porque o programa rodaria por muito tempo antes de dar erro. O algoritmo é simples, mas lentíssimo: ao calcular `fib (n)`, o número de chamadas (recursivas) `fib (1)` ou `fib (2)` que ele vai fazer é igual ao resultado final.

Todavia, você pode rapidamente observar um estouro de pilha usando seguinte função:

```c
int
fill_stack (int n)
{
  if (n <= 1)  /* Limita a profundeza da recursão  */
    return 1;
  else
    return fill_stack (n - 1);
}
```

Com um laptop [Lemote](https://en.wikipedia.org/wiki/Lemote) Yeeloong rodando o sistema operacional gNewSense GNU/Linux com configuração padrão, um experimento demonstrou que há espaço suficiente na pilha para realizar 261906 chamadas aninhadas para essa função. Uma mais e a pilha estoura e o programa é encerrado. Em outra plataforma com uma configuração diferente ou com uma função diferente, o limite pode ser maior ou menor.

{% hint style="info" %}
Em meus testes com o Windows 11 e Visual Studio 2022, a pilha estourou a partir de 4023 chamadas, ou seja, com `fill_stack(4024)`.
{% endhint %}
