---
layout:
  width: default
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
  metadata:
    visible: true
---

# Comparação de Ponteiros

Dois valores de ponteiro são considerados **iguais** se apontam para a **mesma localização**, ou se **ambos são nulos**. Você pode testar isso com os operadores `==` e `!=`. Aqui está um exemplo simples:

```c
{
  int i;
  int *p, *q;

  p = &i;
  q = &i;

  if (p == q)
    printf("Isso será impresso.\n");

  if (p != q)
    printf("Isso não será impresso.\n");
}
```

Comparações de **ordenação**, como `>` e `>=`, operam sobre ponteiros **convertendo-os para inteiros sem sinal**. O padrão da linguagem C diz que os dois ponteiros devem apontar para **dentro do mesmo objeto** na memória. No entanto, em sistemas GNU/Linux, essas operações simplesmente comparam os **valores numéricos dos ponteiros**.

Em princípio, os ponteiros comparados devem ter o **mesmo tipo**, mas diferenças são permitidas em alguns casos limitados:

* Se os **tipos apontados** pelos dois ponteiros forem **quase compatíveis** (veja [_Tipos Compatíveis_](#user-content-fn-1)[^1]), a comparação é permitida.
* Se um dos operandos for do tipo `void *` (veja [_Ponteiros para void_](ponteiros-para-void.md)) e o outro for um ponteiro de outro tipo, o operador de comparação converte o ponteiro `void *` para o tipo do outro operando, para que possam ser comparados.
  * **Obs.:** Em C padrão, isso **não é permitido** se o outro tipo for ponteiro para função, mas no **GNU C** isso funciona.

Os operadores de comparação também permitem comparar o número **inteiro `0`** com um valor de ponteiro. Nesse caso, o `0` é convertido para um **ponteiro nulo** do mesmo tipo do outro operando.

[^1]: Capítulo pendente de tradução
