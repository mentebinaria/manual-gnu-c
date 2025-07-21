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

# Ponteiros e Arrays

A forma mais limpa de se referir a um elemento de um array é usando `array[indice]`. Outra forma, mais complicada, de fazer a mesma coisa é obter o **endereço** desse elemento como um **ponteiro**, e então **desreferenciá-lo**:

```c
*(&array[0] + indice)
```

ou, de forma equivalente:

```c
*(array + indice)
```

Isso obtém primeiro um ponteiro para o elemento zero, depois o incrementa com `+` para apontar para o elemento desejado, e então obtém o valor de lá.

Essa construção com aritmética de ponteiros é, na verdade, a **definição dos colchetes** em C: `a[b]` significa, por definição, `*(a + b)`.

Essa definição trata `a` e `b` de forma **simétrica**: um deles deve ser um ponteiro e o outro, um inteiro — **não importa qual vem primeiro**.

Assim, como a indexação com colchetes é definida em termos de adição e desreferência, ela também é simétrica. Por isso, você pode escrever `3[array]`, que é equivalente a `array[3]`. No entanto, seria tolice escrever `3[array]`, já que isso **não tem nenhuma vantagem** e pode confundir quem lê o código.

Pode parecer contraditório o fato de que `*(a + b)` exige um ponteiro, enquanto `array[3]` usa um valor do tipo array. Por que isso é válido?

Porque o **nome de um array**, quando usado sozinho em uma expressão (exceto em `sizeof`), representa um **ponteiro para o elemento zero do array**. Assim, `array + 3` converte implicitamente `array` para `&array[0]`, e o resultado é um ponteiro para o elemento 3 — equivalente a `&array[3]`.

Como os colchetes são definidos com base nessa adição, `array[3]` primeiro converte `array` para um ponteiro. É por isso que funciona usar um array diretamente nessa construção.
