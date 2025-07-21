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

# Desreferenciando Ponteiros

O principal uso de um valor de ponteiro é desreferenciá-lo (acessar os dados para os quais ele aponta) com o operador unário ‘`*`’. Por exemplo, `*&i` é o valor no endereço de `i` — que é justamente `i`. As duas expressões são equivalentes, desde que `&i` seja válido.

Uma expressão de desreferência de ponteiro cujo tipo é um dado (e não uma função) é um _lvalue_.

Os ponteiros se tornam realmente úteis quando os armazenamos em algum lugar e os usamos depois. Aqui está um exemplo simples para ilustrar essa prática:

```c
{
  int i;
  int *ptr;

  ptr = &i;

  i = 5;

  …

  return *ptr;   /* Retorna 5, obtido de i. */
}
```

Isso mostra como declarar a variável `ptr` com o tipo `int *` (ponteiro para `int`), armazenar nela um valor de ponteiro (apontando para `i`) e usá-lo depois para obter o valor do objeto para o qual ele aponta (o valor em `i`).

Aqui está outro exemplo de uso de um ponteiro para uma variável:

```c
/* Define a variável global i. */
int i = 2;

int
foo (void)
{
  /* Armazena o endereço da variável global i. */
  int *global_i = &i;

  /* Declara uma i local, ocultando a i global. */
  int i = 5;

  /* Imprime o valor da i global e da i local. */
  printf ("global i: %d\nlocal i: %d\n", *global_i, i);
  return i;
}
```

É claro que, em um programa real, seria muito mais limpo usar nomes diferentes para essas duas variáveis, em vez de chamar ambas de `i`. Mas é difícil ilustrar esse ponto sintático com um código “limpo”. Se alguém puder fornecer um exemplo útil para ilustrar isso com mais clareza, ele será bem-vindo.
