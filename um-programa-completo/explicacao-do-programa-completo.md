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

# Explicação do Programa Completo

Aqui está a explicação do código do exemplo na seção anterior.

Este programa de exemplo imprime uma mensagem que mostra o valor de `fib (20)` e termina com o código `0` (que indica uma execução bem-sucedida).

Todo programa em C inicia com a execução da função chamada `main`.  Portanto, o programa de exemplo define uma função chamada `main` para fornecer uma maneira de iniciá-lo. O que essa função faz é o que o programa faz. Veja [A Função main.](#user-content-fn-1)[^1]

A função `main` é a primeira a ser chamada quando o programa é executado, mas ela não é a primeira a ser definida no código de exemplo. A ordem das definições de funções no código-fonte não faz diferença para o significado do programa.

A chamada inicial para `main` sempre passa certos argumentos, mas a `main` não precisa se preocupar com eles. Para ignorar esses argumentos, defina a `main` com `void` como na lista de parâmetros. (`void` como na lista de parâmetros de função normalmente significa "chamar sem argumentos", mas a `main` é um caso especial.)

A função `main` retorna `0` porque essa é a maneira convencional de ela indicar uma execução bem-sucedida. Ela poderia, ao invés disso, retornar um número inteiro positivo para indicar erro, e alguns programas utilitários têm convenções específicas para o significado de certos códigos numéricos de erro. Veja [Valores da main](#user-content-fn-2)[^2].

A maneira mais simples de imprimir texto em C é chamando a função `printf`, então aqui explicamos brevemente o que essa função faz. Para uma explicação completa de `printf` e das outras funções padrão de entrada e sída (E/S), veja a seção "I/O on Streams" no _The GNU C Library Reference Manua_l (disponível somente em inglês).

O primeiro argumento da `printf` é uma constante string ([Strings Constantes](#user-content-fn-3)[^3]) que é um modelo para a saída. A função `printf` copia a maior parte dessa string diretamente para a saída, incluindo o caractere de nova linha no final da string, que é escrito como '\n'. A saída vai para a saída padrão do programa, que comumente é o terminal.

**'%'** no modelo introduz um código que substitui outro texto na saída. Especificamente, **'%d'** significa pegar o próximo argumento da `printf` e substituí-lo no texto como um número decimal. (O argumento para **'%d'** deve ser do tipo **int**; se não for, printf funcionará mal.) Então, a saída será uma linha que se parece com isso:

`O item 20 da série Fibonacci é 6765`

Este programa não contém uma definição para a `printf` porque ela é definida pela biblioteca C, o que a torna disponível em todos os programas em C. No entanto, cada programa precisaria declarar a `printf` para que ela seja chamada corretamente. A linha `#include` cuida disso; ela inclui um arquivo de cabeçalho chamado `stdio.h` no código do programa. Esse arquivo é fornecido pelo sistema operacional e contém declarações para as muitas funções padrão de entrada/saída da biblioteca C, dentre elas a `printf`.

Não se preocupe com arquivos de cabeçalho por agora; explicaremos eles mais tarde em [Arquivos de Cabeçalho](#user-content-fn-4)[^4].

O primeiro argumento da `printf` não precisa ser uma constante string; pode ser qualquer string (veja Strings). No entanto, usar uma constante é o caso mais comum.

[^1]: Capítulo pendente de tradução

[^2]: Capítulo pendente de tradução

[^3]: Capítulo pendente de tradução

[^4]: Capítulo pendente de tradução
