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

# Ponteiros para void

O tipo peculiar `void *`, um ponteiro cujo tipo apontado é `void`, é usado com frequência em C. Ele representa um ponteiro para “não dizemos o quê”. Por exemplo:

```c
void *numbered_slot_pointer(int);
```

declara uma função `numbered_slot_pointer` que recebe um parâmetro inteiro e retorna um ponteiro — mas **não dizemos para que tipo de dado** ele aponta.

As funções de **alocação dinâmica de memória** (veja [_Alocação Dinâmica de Memória_](#user-content-fn-1)[^1]) usam o tipo `void *` para se referir a blocos de memória, independentemente do tipo de dado que o programa armazenará nesses blocos.

Com o tipo `void *`, é possível **passar o ponteiro** adiante e **testar se ele é nulo**. No entanto, desreferenciá-lo fornece um valor `void`, que **não pode ser usado** (veja _O_[ _Tipo `void`_](../11.-tipos-primitivos/o-tipo-void.md)). Para desreferenciar o ponteiro, é necessário **convertê-lo** para algum outro tipo de ponteiro primeiro.

Atribuições convertem automaticamente `void *` para qualquer outro tipo de ponteiro, desde que o operando à esquerda tenha um tipo de ponteiro. Por exemplo:

```c
{
  int *p;
  /* Converte o valor de retorno para int *. */
  p = numbered_slot_pointer(5);
  …
}
```

Ao passar um argumento do tipo `void *` para um parâmetro que exige um tipo de ponteiro específico, também ocorre a conversão. Por exemplo, suponha que a função `hack` tenha sido declarada com um parâmetro do tipo `float *`:

```c
/* Declaramos hack assim.
   Assumimos que está definida em outro lugar. */
void hack(float *);
…
/* Agora chamamos hack. */
{
  /* Converte o valor de retorno de numbered_slot_pointer
     para float * para passá-lo para hack. */
  hack(numbered_slot_pointer(5));
  …
}
```

Também é possível converter para outro tipo de ponteiro usando um _cast_ explícito (veja [_Conversão de Tipo Explícita_](#user-content-fn-1)[^1]), como neste exemplo:

```c
(int *) numbered_slot_pointer(5)
```

Aqui está um exemplo que decide **em tempo de execução** para qual tipo de ponteiro converter:

```c
void
extract_int_or_double(void *ptr, bool its_an_int)
{
  if (its_an_int)
    handle_an_int(*(int *)ptr);
  else
    handle_a_double(*(double *)ptr);
}
```

A expressão `*(int *)ptr` significa: converter `ptr` para o tipo `int *`, depois desreferenciá-lo.

[^1]: Capítulo pendente de tradução
