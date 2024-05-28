# Explicação do Programa Completo

Aqui está a explicação do código do exemplo na seção anterior.

Este programa de exemplo imprime uma mensagem que mostra o valor de `fib (20)` e termina com o código 0 (que indica uma execução bem-sucedida).

Todo programa em C é iniciado executando a função chamada main. Portanto, o programa de exemplo define uma função chamada main para fornecer uma maneira de iniciá-lo. O que essa função faz é o que o programa faz. Veja A Função main.

A função main é a primeira a ser chamada quando o programa é executado, mas ela não vem primeiro no código de exemplo. A ordem das definições de funções no código-fonte não faz diferença para o significado do programa.

A chamada inicial para main sempre passa certos argumentos, mas main não precisa prestar atenção neles. Para ignorar esses argumentos, defina main com void como a lista de parâmetros. (void como uma lista de parâmetros de função normalmente significa "chamar sem argumentos", mas main é um caso especial.)

A função main retorna 0 porque essa é a maneira convencional de main indicar execução bem-sucedida. Ela poderia, em vez disso, retornar um número inteiro positivo para indicar falha, e alguns programas utilitários têm convenções específicas para o significado de certos códigos numéricos de falha. Veja Valores de main.

A maneira mais simples de imprimir texto em C é chamando a função printf, então aqui explicamos brevemente o que essa função faz. Para uma explicação completa de printf e das outras funções padrão de E/S, veja A Biblioteca C GNU no Manual de Referência da Biblioteca C GNU.

O primeiro argumento para printf é uma constante de string (veja Constantes de String) que é um modelo para a saída. A função printf copia a maior parte dessa string diretamente como saída, incluindo o caractere de nova linha no final da string, que é escrito como '\n'. A saída vai para o destino de saída padrão do programa, que no caso usual é o terminal.

'%' no modelo introduz um código que substitui outro texto na saída. Especificamente, '%d' significa pegar o próximo argumento para printf e substituí-lo no texto como um número decimal. (O argumento para '%d' deve ser do tipo int; se não for, printf funcionará mal.) Então, a saída é uma linha que se parece com isso:

O item 20 da série Fibonacci é 6765 Este programa não contém uma definição para printf porque ela é definida pela biblioteca C, o que a torna disponível em todos os programas C. No entanto, cada programa precisa declarar printf para que ela seja chamada corretamente. A linha #include cuida disso; ela inclui um arquivo de cabeçalho chamado stdio.h no código do programa. Esse arquivo é fornecido pelo sistema operacional e contém declarações para as muitas funções padrão de entrada/saída na biblioteca C, uma das quais é printf.

Não se preocupe com arquivos de cabeçalho por agora; explicaremos eles mais tarde em Arquivos de Cabeçalho.

O primeiro argumento de printf não precisa ser uma constante de string; pode ser qualquer string (veja Strings). No entanto, usar uma constante é o caso mais comum.
