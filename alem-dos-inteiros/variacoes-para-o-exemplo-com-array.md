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

# Variações para o Exemplo com Array

O código para chamar a função `avg_of_double` tem duas declarações que começam com o mesmo tipo de dado:

```c
  /* O array de valores para calcular a média.  */
  double nums_to_average[5];
  /* A média, uma vez que a calculamos.  */
  double average;
```

Em C, você pode combinar as duas, assim:

```c
  double nums_to_average[5], average;
```

Isso declara `nums_to_average` para que cada um de seus elementos seja um `double`, e `average` para que seja simplesmente um `double`.

No entanto, embora você possa combiná-las, isso não significa que deva. Se for útil escrever comentários sobre as variáveis, e geralmente é, então é melhor manter as declarações em linhas separadas para que você possa colocar um comentário em cada uma. Isso também ajuda ao usar editores de texto para encontrar ocorrências de uma variável nos arquivos de código-fonte.

{% hint style="info" %}
Em arquivos grandes de código-fonte, pode ser que você queira encontrar o momento da declaração de uma variável utilizando um editor de texto como vim, Visual Studio Code, Notepad++, etc. Por exemplo, você pode buscar por `int num` para buscar a declaração de uma variável chamada `num`, que é tipo `int`. No entanto, se você declarar mais de uma variável na mesma linha como em `int i, num, j;`, a busca por `int num` não encontraria esta ocorrência. Além da clareza, este é o motivo pelo qual os autores desencorajam este tipo de declaração.
{% endhint %}

Definimos então todos os elementos do array `nums_to_average` com atribuições, mas é mais conveniente usar um inicializador na declaração:

```c
{
  /* O array de valores para calcular a média.  */
  double nums_to_average[]
    = { 58.7, 5.1, 7.7, 105.2, -3.14159 };

  /* A média, uma vez que a calculamos.  */
  double average = avg_of_double ((sizeof (nums_to_average)
                                   / sizeof (nums_to_average[0])),
                                  nums_to_average);

  /* …agora faça uso da média… */
}
```

O inicializador do array é uma lista de valores separados por vírgulas, delimitados por chaves. Veja Inicializadores[^1].

Note que a declaração não especifica um tamanho para `nums_to_average`, então o tamanho é determinado a partir do inicializador. Há cinco valores no inicializador, então `nums_to_average` recebe o comprimento 5. Se adicionarmos outro elemento ao inicializador, `nums_to_average` terá seis elementos.

Como o código calcula o número de elementos a partir do tamanho do array, usando `sizeof`, o programa operará em todos os elementos no inicializador, independentemente de quantos sejam.

{% hint style="info" %}
No código de exemplo, uma certa aritimética é utilizada para pegar o tamanho do array, que é 5,  já que este é inicializado com 5 elementos. A técnica consiste em utilizar o operador `sizeof`, que retorna o tamanho de um tipo em tempo de compilação, diretamente no array e dividir esse resultado pelo tamanho de qualquer um dos elementos do array, já que todos são do mesmo tipo (normalmente o primeiro elemento, de índice 0, é o escolhido).

Para entender como isto functiona, suponha que uma variável do tipo `double` ocupe 8 bytes de memória. Isso significa que um array de double com 5 elementos vai ocupar 40 bytes. Ao dividir 40 pelo tamanho de um dos elementos, que é 8, você obtém o número de elementos do array, que é 5 neste caso.

Fazer isso faz com que você possa adicionar ou remover elementos na inicialização do array sem se preocupar em atualizar o valor do tamanho do array, já que as operações com o `sizeof` irão calcular o tamanho do array novamente.

Só lembre-se que isto é em tempo de compilação, ou seja, é preciso recompilar o programa para alterar os elementos com os quais o array é inicializado. Só assim `sizeof` retornará o valor atualizado do tamanho do array.
{% endhint %}

{% embed url="https://www.youtube.com/watch?v=GARkpT6-x-g" %}



[^1]: Capítulo pendente de tradução
