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

# 🟰 Expressões de Atribuição

Como conceito geral em programação, uma atribuição é uma construção que armazena um novo valor em um local onde valores podem ser armazenados — por exemplo, em uma variável. Esses locais são chamados de _lvalues_ (veja [_Lvalues_](#user-content-fn-1)[^1]) porque são locais (por isso o "l") que armazenam um valor.

Uma atribuição em C é uma expressão porque possui um valor; chamamos isso de expressão de atribuição. Uma atribuição simples se parece com:

```c
lvalue = valor-para-armazenar
```

Dizemos que ela atribui o valor da expressão `valor-para-armazenar` ao local `lvalue`, ou que armazena `valor-para-armazenar` lá. Você também pode pensar no "l" de "lvalue" como significando "esquerda" _(left)_, já que é o que você coloca no lado esquerdo do operador de atribuição.

No entanto, essa não é a única forma de usar um _lvalue_, e nem todos os _lvalues_ podem ser atribuídos. Para usar o _lvalue_ no lado esquerdo de uma atribuição, ele precisa ser modificável. Em C, isso significa que ele não foi declarado com o qualificador de tipo `const` (veja [_const_](#user-content-fn-2)[^2]).

O valor da expressão de atribuição é o de `lvalue` após o novo valor ser armazenado nele. Isso significa que você pode usar uma atribuição dentro de outras expressões. Os operadores de atribuição são associativos à direita, de modo que:

```c
x = y = z = 0;
```

é equivalente a:

```c
x = (y = (z = 0));
```

Essa é a única maneira útil para associá-los; a outra maneira,

```c
((x = y) = z) = 0;
```

seria inválida, pois uma expressão de atribuição como `x = y` não é válida como um _lvalue_.

{% hint style="info" %}
Quando o texto diz que o valor de expressão de atribuição é o de `lvalue`, quer dizer que a expressão "retorna" o `lvalue`. Por exemplo, `i = 10` "retorna" 10. Ou seja, se essa expressão de atribuição inteira for utilizada à direita de um operador de atribuição, o valor dela será `10`.
{% endhint %}

Aviso: Coloque parênteses ao redor de uma atribuição se você a aninhar dentro de outra expressão, a menos que seja uma expressão condicional, uma série separada por vírgulas ou outra atribuição.

[^1]: Capítulo pendente de tradução

[^2]: Capítulo pendente de tradução
