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

# Endereço dos Dados

A forma mais básica de criar um ponteiro é com o operador “de endereço”, ‘&’. Suponha que temos as seguintes variáveis disponíveis:

```c
int i;
double a[5];
```

Agora, `&i` fornece o endereço da variável `i` — um valor de ponteiro que aponta para a localização de `i` — e `&a[3]` fornece o endereço do elemento 3 de `a`. (Pela convenção usual de numeração em inglês com origem no 1, esse é na verdade o quarto elemento do array, já que o elemento inicial tem índice 0.)

O operador de endereço é incomum porque opera sobre um local para armazenar um valor (um _lvalue_, veja [Lvalues](../7.-expressoes-de-atribuicao/lvalues.md)), e não sobre o valor atualmente armazenado ali. (O argumento à esquerda de uma atribuição simples também é incomum por esse mesmo motivo.) Você pode usá-lo sobre qualquer _lvalue_, exceto um campo de bits (veja Campos de Bits) ou um construtor (veja [Construtores de Estruturas](#user-content-fn-1)[^1]).

[^1]: Capítulo pendente de tradução
