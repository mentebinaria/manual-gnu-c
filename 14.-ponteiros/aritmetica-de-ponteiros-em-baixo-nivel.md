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

# Aritmética de Ponteiros em Baixo Nível

O comportamento da **aritmética de ponteiros** é, **teoricamente**, definido apenas quando os ponteiros envolvidos apontam para **dentro de um mesmo objeto** alocado na memória. Mas os operadores de adição e subtração **não têm como saber** se os ponteiros estão todos dentro de um único objeto — eles **não sabem onde os objetos começam ou terminam**. Então, o que esses operadores fazem **de fato**?

Ao somar um ponteiro `p` com um inteiro `i`, o compilador trata `p` como um **endereço de memória**, que na prática é um valor inteiro — vamos chamá-lo de `pint`. O valor `i` é tratado como uma **quantidade de elementos** do tipo para o qual `p` aponta. O total de bytes corresponde a `i * sizeof(*p)`. O resultado da soma, como inteiro, é:

```
pint + i * sizeof(*p)
```

Esse valor é então reinterpretado como um **ponteiro do mesmo tipo de `p`**.

Se o ponteiro inicial `p` e o resultado da operação **não apontarem para partes do mesmo objeto**, a operação **não é oficialmente legítima**, e programas em C **não deveriam fazer isso**. Mas você **pode fazer** mesmo assim — e ela produzirá exatamente o resultado descrito acima.

Em certas situações especiais, isso pode ser útil — mas quem **não for experiente** deve evitar esse tipo de prática.

**Exemplo: função para somar ponteiros em baixo nível**

Aqui está uma função que desloca um valor de ponteiro como se ele apontasse para um objeto de tamanho arbitrário, realizando explicitamente esse cálculo:

```c
#include <stdint.h>

void *
ptr_add(void *p, int i, int objsize)
{
  intptr_t p_address = (long) p;
  intptr_t totalsize = i * objsize;
  intptr_t new_address = p_address + totalsize;
  return (void *) new_address;
}
```

Essa função realiza o mesmo trabalho que `p + i`, desde que `p` tenha o tipo de ponteiro adequado. Ela usa o tipo `intptr_t`, definido no cabeçalho `<stdint.h>`. (**Na prática**, `long long` funcionaria, mas é mais limpo e seguro usar `intptr_t`.)
