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

# Um Exemplo com Arrays

Uma função para calcular a média de três números é muito específica e limitada. Uma função mais geral calcularia a média de qualquer quantidade de números. Isso requer passar os números em um array. Um array é um objeto na memória que contém uma série de valores do mesmo tipo de dado. Este capítulo apresenta os conceitos básicos e o uso de arrays através de um exemplo; para a explicação completa, veja Arrays[^1].

Aqui está a definição de uma função para calcular a média de vários números de ponto flutuante, passados como tipo `double`. O primeiro parâmetro, `length`, especifica quantos números são passados. O segundo parâmetro, `input_data`, é um array que contém esses números.

```c
double
avg_of_double (int length, double input_data[])
{
  double sum = 0;
  int i;

  for (i = 0; i < length; i++)
    sum = sum + input_data[i];

  return sum / length;
}
```

O código anterior introduz a expressão para se referir a um elemento de um array: `input_data[i]` significa o elemento de índice `i` no array `input_data`. O índice do elemento pode ser qualquer expressão com um valor inteiro; neste caso, a expressão é `i`. Veja [Acessando Elementos do Array](#user-content-fn-2)[^2].

O índice menor índice válido em um array é 0, _não_ 1, e o maior índice válido é um a menos que o número de elementos. (Isso é conhecido como _indexação com origem zero_.)

Este exemplo também introduz a maneira de declarar que um parâmetro de função é um array. Tal  declaração é feita após o nome do parâmetro. Assim como `double foo` declara que `foo` é do tipo `double`, `double input_data[]` declara que cada elemento de `input_data` é do tipo `double`. Portanto, `input_data` em si tem o tipo "array de double".

{% hint style="info" %}
É muito comum em textos técnicos em inglês você encontrar as palavras _foo_, _bar_ ou _foobar_. Elas são utilizadas para passar uma ideia de "qualquer coisa", ou "qualquer nome", ou seja, a ideia de que o nome não importa. Em português, seria equivalente ao modo como nos referenciamos a pessoas desconhecidas com "fulano" ou "cicrano".
{% endhint %}

Ao declarar um parâmetro que é um array, não é necessário dizer qual é o comprimento do array. Neste caso, o parâmetro `input_data` não tem informação de comprimento. É por isso que a função precisa de outro parâmetro, `length`, para que o chamador forneça essa informação para a função `avg_of_double`.

{% hint style="info" %}
O nome _avg\_of\_double_ é uma forma abrevidada de _average of double_. Em inglês, _average_ é _média_. Já _length_, traduz para tamanho (no caso do código de exemplo, tamanho do array -em outras palavras, o número de elementos do array). Temos também _input\_data_ (dados de entrada) e _sum_ (soma).
{% endhint %}

[^1]: Capítulo pendente de tradução

[^2]: Capítulo pendente de tradução
