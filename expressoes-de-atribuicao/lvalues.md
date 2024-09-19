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

# Lvalues

Uma expressão que identifica um espaço de memória que armazena um valor é chamada de _lvalue_, porque é uma localização que pode armazenar um valor.

Os tipos padrão de _lvalues_ são:

* Uma variável.
* Uma expressão de desreferenciamento de ponteiro (veja [Desreferenciamento de Ponteiro](#user-content-fn-1)[^1]) usando o unário ‘\*’.
* Uma referência a um campo de estrutura (veja Estruturas[^2]) usando ‘.’, se o valor da estrutura for um _lvalue_.
* Uma referência a um campo de estrutura usando ‘`->`’. Isso é sempre um _lvalue_ já que ‘`->`’ implica desreferenciamento de ponteiro.
* Uma referência a uma alternativa de união (veja Uniões[^3]), nas mesmas condições que para campos de estruturas.
* Uma referência a um elemento de um array usando ‘\[…]’, se o array for um _lvalue_.

Se a operação mais externa de uma expressão for qualquer outro operador, essa expressão não é um _lvalue_. Assim, a variável `x` é um _lvalue_, mas `x + 0` não é, mesmo que essas duas expressões calculem o mesmo valor (supondo que `x` seja um número).

Um array pode ser um _lvalue_ (as regras acima determinam se ele é um), mas usar o array em uma expressão o converte automaticamente em um ponteiro para o elemento zero. O resultado dessa conversão não é um _lvalue_. Portanto, se a variável `a` for um array, você não pode usá-la sozinha como o operando esquerdo de uma atribuição. Mas você pode atribuir a um elemento de `a`, como `a[0]`. Isso é um _lvalue_, já que `a` é um _lvalue_.

[^1]: Capítulo pendente de tradução

[^2]: Capítulo pendente de tradução

[^3]: Capítulo pendente de tradução
