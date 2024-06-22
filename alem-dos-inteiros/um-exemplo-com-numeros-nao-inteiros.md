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

# Um Exemplo com Números Não Inteiros

Aqui está uma função que opera e retorna números de _ponto flutuante_ que não precisam ser, necessariamente, inteiros. Ponto flutuante é uma maneira de representa um número como uma fração juntamente com uma potência de 2. (Para mais detalhes, veja [Tipos de Dados de Ponto Flutuante](#user-content-fn-1)[^1].) Este exemplo calcula a média de três números de ponto flutuante que são passados para a função como argumentos:

```c
double
average_of_three (double a, double b, double c)
{
  return (a + b + c) / 3;
}
```

Os valores dos parâmetros _a_, _b_ e _c_ não precisam ser inteiros e, mesmo quando são inteiros, provavelmente a média deles não o é.

`double` é o tipo de dado usual em C para cálculos com números de ponto flutuante.

Para imprimir um `double` com a função `printf`, devemos usar '%f' em vez de '%d':

```c
printf ("A média é %f\n",
        average_of_three (1.1, 9.8, 3.62));
```

O código que chama a `printf` deve passar um `double` para impressão com '%f' e um `int` para impressão com '%d'. Se o argumento tiver o tipo errado, a `printf` produzirá uma saída sem sentido.

Aqui está um programa completo que calcula a média de três números específicos e imprime o resultado:

```c
double
average_of_three (double a, double b, double c)
{
  return (a + b + c) / 3;
}

int
main (void)
{
    printf ("A média é %f\n",
            average_of_three (1.1, 9.8, 3.62));
    return 0;
}
```

A partir de agora, não mostrares mais exemplos de chamadas às funções que escrevemos na função `main`. Em vez disso, encorajamos você a escrevê-las por conta própria quando quiser testar a execução de algum código.

[^1]: Capítulo pendente de tradução
