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

# Operador Vírgula

O operador vírgula representa a execução sequencial de expressões. O valor da expressão com vírgula vem da última expressão da sequência; as expressões anteriores são calculadas apenas por seus efeitos colaterais. Ele se parece com isto:

```c
exp1, exp2 …
```

Você pode agrupar qualquer número de expressões dessa forma, colocando vírgulas entre elas.

## Os Usos do Operador Vírgula

Com vírgulas, você pode colocar várias expressões em um lugar que exige apenas uma expressão — por exemplo, no cabeçalho de uma instrução `for`. Esta instrução

```c
for (i = 0, j = 10, k = 20; i < n; i++)
```

contém três expressões de atribuição para inicializar `i`, `j` e `k`. A sintaxe de `for` exige apenas uma expressão para inicialização; para incluir três atribuições, usamos vírgulas para agrupá-las em uma única expressão maior: `i = 0, j = 10, k = 20`. Essa técnica também é útil na expressão de avanço do laço, a última das três dentro dos parênteses do `for`.

Na instrução `for` e na instrução `while` (veja Instruções de Laço), uma vírgula fornece uma maneira de realizar algum efeito colateral antes do teste de saída do laço. Por exemplo,

```c
while (printf ("No teste, x = %d\n", x), x != 0)
```

## Uso Limpo do Operador Vírgula

Sempre escreva parênteses ao redor de uma série de operadores vírgula, exceto quando estiverem no nível superior em uma instrução de expressão, ou dentro dos parênteses de uma instrução `if`, `for`, `while` ou `switch` (veja Instruções[^1]). Por exemplo, em

```c
for (i = 0, j = 10, k = 20; i < n; i++)
```

as vírgulas entre as atribuições são claras porque estão entre um parêntese e um ponto e vírgula.

Os argumentos em uma chamada de função também são separados por vírgulas, mas isso não é um caso do operador vírgula. Note a diferença entre

```c
foo (4, 5, 6)
```

que passa três argumentos para `foo` e

```c
foo ((4, 5, 6))
```

que usa o operador vírgula e passa apenas um argumento (com valor 6).

**Aviso:** não use o operador vírgula ao redor de um argumento de função, a menos que isso torne o código mais legível. Quando o fizer, não coloque parte de outro argumento na mesma linha. Em vez disso, adicione uma quebra de linha para tornar os parênteses ao redor do operador vírgula mais fáceis de ver, como neste exemplo:

```c
foo ((mumble (x, y), frob (z)),
     *p)
```

## Quando Não Usar o Operador Vírgula

Você pode usar uma vírgula em qualquer subexpressão, mas, na maioria dos casos, isso apenas torna o código confuso, e é mais claro elevar todas as expressões separadas por vírgula, exceto a última, para um nível mais alto. Assim, em vez disso:

```c
x = (y += 4, 8);
```

é muito mais claro escrever assim:

```c
y += 4, x = 8;
```

ou assim:

```c
y += 4;
x = 8;
```

Use vírgulas apenas nos casos em que não haja alternativa mais clara envolvendo múltiplas instruções.

Por outro lado, não hesite em usar vírgulas na expansão de uma definição de macro. As compensações em termos de clareza de código são diferentes nesse caso, porque o uso da macro pode melhorar tanto a clareza geral que a "feiúra" da definição da macro é um pequeno preço a pagar. Veja Macros[^2].

[^1]: Capítulo pendente de tradução

[^2]: Capítulo pendente de tradução
