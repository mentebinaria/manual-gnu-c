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

# Ponteiros Nulos

Um valor de ponteiro pode ser **nulo**, o que significa que ele **não aponta para nenhum objeto**. A forma mais limpa de obter um ponteiro nulo é escrevendo `NULL`, uma macro padrão definida em `<stddef.h>`. Também é possível fazer isso convertendo o valor `0` para o tipo de ponteiro desejado, como em:

```c
(char *) 0
```

(O operador de _cast_ realiza a conversão explícita de tipo; veja [Conversão de Tipo Explícita](#user-content-fn-1)[^1].)

Você pode armazenar um ponteiro nulo em qualquer _lvalue_ cujo tipo de dado seja um tipo de ponteiro:

```c
char *foo;
foo = NULL;
```

Essas duas linhas, se forem consecutivas, podem ser combinadas em uma declaração com inicializador:

```c
char *foo = NULL;
```

Também é possível fazer o _cast_ explícito de `NULL` para o tipo de ponteiro específico desejado — isso **não faz diferença**:

```c
char *foo;
foo = (char *) NULL;
```

Para testar se um ponteiro é nulo, compare-o com zero ou com `NULL`, como no exemplo abaixo:

```c
if (p != NULL)
  /* p não é nulo. */
  operate(p);
```

Como testar se um ponteiro **não é nulo** é algo básico e frequente, todos, exceto iniciantes em C, entenderão a forma abreviada sem `!= NULL`:

```c
if (p)
  /* p não é nulo. */
  operate(p);
```

[^1]: Capítulo pendente de tradução
