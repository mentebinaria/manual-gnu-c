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

# Incremento e Decremento de Ponteiros

O operador `++` adiciona 1 a uma variável. Já vimos seu uso com inteiros (veja [_Operadores de Incremento e Decremento_](../7.-expressoes-de-atribuicao/operadores-de-incremento-e-decremento.md)), mas ele também funciona com **ponteiros**. Por exemplo, suponha que temos uma série de inteiros positivos, terminada por zero, e queremos somá-los. Aqui está uma forma simples de percorrer esse array **avançando um ponteiro**:

```c
int
sum_array_till_0(int *p)
{
  int sum = 0;

  for (;;)
    {
      /* Busca o próximo inteiro. */
      int next = *p++;
      /* Sai do laço se for 0. */
      if (next == 0)
        break;
      /* Adiciona ao total acumulado. */
      sum += next;
    }

  return sum;
}
```

A instrução `break;` será explicada mais adiante (veja [_Instrução break_](#user-content-fn-1)[^1]). Nesse uso, ela **interrompe imediatamente** o `for` mais próximo.

A expressão `*p++` usa o **pós-incremento** (`++`; veja [_Pós-incremento e Pós-decremento_](../7.-expressoes-de-atribuicao/pos-incremento-e-pos-decremento.md)) no ponteiro `p`. Ela é interpretada como `*(p++)`, pois operadores pós-fixados têm precedência sobre os prefixados. Portanto, primeiro é feita a **desreferência do valor atual de `p`**, e **só depois `p` é incrementado**.

Incrementar um ponteiro significa somar 1 a ele, como em `p = p + 1`. Como `p` é um ponteiro, somar 1 a ele o **avança pelo tamanho do dado apontado** — neste caso, `sizeof(int)`. Assim, cada iteração do laço busca o próximo inteiro da sequência e o armazena em `next`.

Esse `for` não tem expressão de **inicialização** (pois `p` e `sum` já estão inicializados), nem de **condição final** (o `break` faz isso), nem de **avanço explícito** (que é feito dentro do laço com `p++` e `sum += next`). Por isso, as três expressões no cabeçalho do `for` são deixadas vazias.

***

Outra forma de escrever essa função é **mantendo `p` fixo** e usando **indexação** para acessar os inteiros no array:

```c
int
sum_array_till_0_indexing(int *p)
{
  int i;
  int sum = 0;

  for (i = 0; ; i++)
    {
      /* Busca o próximo inteiro. */
      int next = p[i];
      /* Sai do laço se for 0. */
      if (next == 0)
        break;
      /* Adiciona ao total acumulado. */
      sum += next;
    }

  return sum;
}
```

Nesse programa, ao invés de avançar `p`, avançamos `i` e o somamos a `p`. (Lembre-se que `p[i]` equivale a `*(p + i)`.) De qualquer forma, o endereço usado para buscar o próximo inteiro é o mesmo.

Não faz diferença nesse código usar `i++` ou `++i`, já que o valor da expressão **não é usado**. O incremento é feito apenas pelo efeito colateral.

***

O operador `--` também funciona com ponteiros, e pode ser usado para **voltar** por um array, como no exemplo abaixo:

```c
int
after_last_nonzero(int *p, int len)
{
  /* Configura q para apontar logo após o último elemento. */
  int *q = p + len;

  while (q != p)
    /* Recuar q até encontrar um elemento diferente de zero. */
    if (*--q != 0)
      /* Retorna o índice do elemento após o último não zero. */
      return q - p + 1;

  return 0;
}
```

Essa função retorna o **tamanho da parte não nula** do array especificado por seus argumentos — isto é, o índice do primeiro zero na sequência final de zeros.

[^1]: Capítulo pendente de tradução
