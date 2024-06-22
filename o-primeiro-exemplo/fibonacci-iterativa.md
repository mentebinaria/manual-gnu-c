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

# Fibonacci Iterativa

Aqui vai um algoritmo muita mais rápido para computar a mesma sequência de Fibonacci. Ele é mais rápido por duas razões. Primeiro, ele usa _iteração_ (isto é, repetição) ao invés de recursão, então ele não consome o tempo de um número alto de chamadas de função, mas principalmente, ele é mais rápido porque o número de repetições é pequeno - somente `n`.

```c
int
fib (int n)
{
  int ultimo = 1;   /* O valor inicial é fib (1).  */
  int anterior = 0;   /* O valor inicial controla fib (2).  */
  int i;

  for (i = 1; i < n; ++i)
    /* Se n é 1 ou menos, a repetição executa zero vezes
    /* já que i < n é falso logo na primeira vez. */
    {
      /* Agora ultimo é fib (i)
         e anterior é fib (i - 1).  */
      /* Calcula fib (i + 1).  */
      int proximo = anterior + ultimo;
      /* Troca os valores.  */
      anterior = ultimo;
      ultimo = proximo;
      /* Agora ultimo é fib (i + 1)
         e anterior é fib (i).
         Mas isso não vai ficar assim por muito tempo
         porque estamos prestes a incrementar i.  */
    }

  return ultimo;
}
```

Essa definição calcula `fib (n)` num tempo proporcional à `n`. Os comentários na definição explicam  como ela funciona: ela avança através da série sempre mantendo os últimos dois valores em `ultimo` e `anterior`, e os soma para obter o próximo valor.

Aqui vão os recursos adicionais da linguagem C que essa definição utiliza:

#### **Blocos internos**

Dentro de uma função, onde um comando é chamado, você pode escrever um _bloco_. Seu formato é `{ ... }` e ele contém zero ou mais comandos e declarações. (Você também pode utilizar blocos adicionais como comandos dentro de um bloco.)

O corpo da função também contém um bloco, que é a razão deste conter comandos e declarações.

Veja Blocos[^1].

#### **Declarações de variáveis locais**

O corpo da função contém tanto declarações quanto comandos. Há três declarações diretamente no corpo da função, assim como uma quarta declaração num bloco interno. Cada declaração começa com `int` porque isso declara uma variável cujo tipo é inteiro. Uma declaração pode declarar várias variáveis, mas cada uma dessas declara somente uma variável.

Variáveis declaradas dentro de um bloco (seja ele o que define o corpo de uma função ou um bloco interno) são _variáveis locais_. Estas variáveis existem somente dentro daquele bloco; seus nomes não estão definidos fora daquele bloco e sair do bloco desaloca a memória ocupada por elas. Este exemplo declara quatro variáveis locais: `ultimo`, `anterior`, `i` e `proximo`.  &#x20;

A declaração de variável local mais básica é assim:

```
tipo nomedavariavel;
```

Por exemplo,

```c
int i;
```

declara a variável local `i` como um inteiro. Veja [Declarações de Variáveis](#user-content-fn-2)[^2].

#### **Inicializadores**

Quando você declara uma variável, você também pode especificar seu valor inicial, assim:

```
tipo nomedavariavel = valor;
```

Por exemplo,

```c
int ultimo = 1;
```

declara a variável local `ultimo` como inteiro (tipo `int`) e a inicializa com o valor 1. Veja Inicializadores.

#### **Atribuição**

Atribuição: um tipo de expressão específica, escrita com o operador `=`, que armazena um novo valor numa variável ou em outro lugar. Portanto,

```c
variavel = valor
```

é uma expressão que computa `valor` e armazena o valor na `variável`. Veja [Expressões de Atribuição](#user-content-fn-3)[^3].

#### **Comandos de expressão**

Um comando de expressão é uma expressão seguida de um ponto-e-vírgula. Isso computa o valor da expressão e na sequência ignora este valor.

Um comando de expressão é útil quando a expressão muda algum dado ou tem outros efeitos colaterais — por exemplo, com chamadas de função ou com atribuições como neste exemplo. Veja [Comando de Expressão](#user-content-fn-4)[^4].

Não faz sentido usar uma expresão sem efeitos colaterais num comando de expressão, exceto em casos muito especiais. Por exemplo, o comando de expressão `x;` examinaria o valor de `x` e o ignoraria.

#### **Operator de incremento**

O operador de incremento é o `++`. A expressão `++i` é uma forma abreviada de `i = i + 1`. Veja Incremento/Decremento[^5].

#### Comando `for`

O comando `for` é uma maneira clara de executar um comando repetidamente—um laço (ver Comandos de Laço). Especificamente,

```
for (i = 1; i < n; ++i)
  corpo
```

começa fazendo `i = 1` (põe o um em `i` ) para preparar o laço. O laço em si consiste em

* Testar `i < n` e sair do laço se isso for falso.
* Executar corpo.
* Avançar o laço (executar `++i`, que incrementa `i`).

O resultado é executar corpo com 1 em `i`, então com 2 em `i` e assim sucessivamente, parando imediatamente antes da repetição quando `i` for igual a `n`. Se `n` é menor que 1, o laço vai executar o corpo zero vezes.

O corpo do laço `for` precisa ser um e somente um comando. Você não pode escrever dois comandos numa mesma linha nele; se você tentar, somente o primeiro deles será tratado como parte do laço.

A forma de colocar múltiplos comandos no laço `for` é agrupá-los como um bloco e é isso que fazemos neste exemplo.

[^1]: Capítulo pendente de tradução

[^2]: Capítulo pendente de tradução

[^3]: Capítulo pendente de tradução

[^4]: Capítulo pendente de tradução

[^5]: Capítulo pendente de tradução
