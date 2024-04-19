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

# Corpo da Função

O resto da definição da função é chamado de _corpo da função_. Como qualquer corpo de função, este inicia com um `{` , termina com um `}` e contém zero ou mais _comandos_ e _declarações_. Comandos especificam ações que o programa deve tomar. Declarações definem nomes de variáveis, funções, etc. Cada comando e cada declaração termina com um ponto-e-vírgula (`;`).

Comandos e declarações frequentemente contém _expressões_; uma expressão é uma construção cuja execução produz um _valor_ de algum tipo, mas também pode causar ações por meio de "efeitos colaterais" que alteram a execução subsequente. Diferentemente, um comando, não tem um valor; ele afeta a execução do programa somente através das ações que ele gera.

O corpo desta função `fib` não contém declarações e contém somente um comando, mas este é um comando complexo uma vez que ele contém comandos aninhados. Essa função utiliza dois tipos de comandos:

`return`&#x20;

O comando `return` faz a função retornar imediatamente. Ele normalmente aparece assim:

```
return valor;
```

Seu objetivo é computar o valor da expressão e sair da função, fazendo-a retornar o valor da expressão produzida. Por exemplo:

```
return 1;
```

faz a função retornar o inteiro 1 e

```
return fib (n - 1) + fib (n - 2);
```

faz a função retornar um valor computado ao fazer a soma dos resultados e duas chamadas de função, como especificado.

`if…else`

O comando `if`…`else` é um _condicional_. Sempre que ele executa, ele escolhe um dos seus dois sub-comandos para executar e ignora o outro. Veja:

```
if (condicional)
  comando-se-verdadeiro
else
  comando-se-falso
```

O que ele faz é computar a expressão condicional e, se der "verdadeiro", ele executa o comando-se-verdadeiro. Do contrário, executa o comando-se-falso. Veja Comando if-else.

Dentro do comando `if`…`else`, condicional é simplesmente uma expressão. Ela é considerada "verdadeira" se seu valor for diferente de zero. (Uma operação de comparação como em `n <= 2`, produz o valor 1 se for "verdadeiro" e 0 se for "falso.” Veja Comparações Numéricas.) Portanto,

```c
if (n <= 2)
  return 1;
else
  return fib (n - 1) + fib (n - 2);
```

primeiro testa se o valor de `n` é menor ou igual a 2. Se sim, a expressão `n <= 2` tem valor 1. Daí a execução continua com o comando

```c
return 1;
```

Do contrário, a execução continua com o comando:

```c
return fib (n - 1) + fib (n - 2);
```

Cada um desses comandos encerra a execução da função e provê um valor para que ela retorne. Veja Comando return.

Calcular `fib(n)`, que utiliza inteiros, funciona apenas quando `n < 47` porque o resultado de `fib (47)` é muito grande para caber num tipo `int`. A operação de adição ao tentar somar `fib (46)` e `fib (45)` não consegue produzir o resultado correto. Isto é chamado de _estouro de inteiro (integer overflow)_.

Estouros podem se manifestar de várias maneiras, mas uma coisa que eles não fazem é produzir o resultado correto já que este não cabe no espaço reservado para o valor. Veja Estouro de Inteiro.

Veja Funções para uma explicação completa sobre funções.
