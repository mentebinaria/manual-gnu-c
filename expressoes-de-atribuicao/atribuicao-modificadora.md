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

# Atribuição Modificadora

Você pode abreviar a construção comum

```c
lvalue = lvalue + expressão
```

como

```c
lvalue += expressão
```

Isso é conhecido como uma _atribuição modificadora_. Por exemplo,

```c
i = i + 5;
i += 5;
```

mostra duas instruções equivalentes. A primeira usa atribuição simples; a segunda usa atribuição modificadora.

A atribuição modificadora funciona com qualquer operador aritmético binário. Por exemplo, você pode subtrair algo de um _lvalue_ assim:

```c
lvalue -= expression
```

ou multiplicá-lo por uma certa quantia assim:

```c
lvalue *= expression
```

ou deslocá-lo por uma certa quantia assim:

```c
lvalue <<= expression
lvalue >>= expression
```

Na maioria dos casos, esse recurso não adiciona mais poder à linguagem, mas fornece uma conveniência substancial. Além disso, quando o _lvalue_ contém código que possui efeitos colaterais, a atribuição simples executa esses efeitos colaterais duas vezes, enquanto a atribuição modificadora os executa apenas uma vez. Por exemplo,

```c
x[foo ()] = x[foo ()] + 5;
```

chama `foo` duas vezes, e ele pode retornar valores diferentes a cada vez. Se `foo ()` retornar 1 na primeira vez e 3 na segunda vez, o efeito pode ser somar `x[3]` e 5 e armazenar o resultado em `x[1]`, ou somar `x[1]` e 5 e armazenar o resultado em `x[3]`. Não sabemos qual dos dois ocorrerá, porque C não especifica qual chamada a `foo` é computada primeiro.

Tal instrução não é bem definida e não deve ser usada.

Por outro lado,

```c
x[foo ()] += 5;
```

é bem definida: chama `foo` apenas uma vez para determinar qual elemento de `x` ajustar, e ajusta esse elemento somando 5 a ele.
