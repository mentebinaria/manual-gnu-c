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

# Constantes do Tipo String

Uma constante do tipo string representa uma série de caracteres. Ela começa com ‘"’ e termina com ‘"’; entre esses delimitadores estão os conteúdos da string. Caracteres especiais como ‘"’, ‘\’ e nova linha podem ser escapados nas constantes do tipo string da mesma forma que nas constantes de caracteres. Em uma constante do tipo string, ‘'’ não precisa ser escapado.

Uma constante do tipo string define um array de caracteres que contém os caracteres especificados seguidos pelo caractere nulo (código 0). Usar a constante do tipo string é equivalente a usar o nome de um array com esses conteúdos. Em casos simples, onde não há sequências de escape com barra invertida, o comprimento em bytes da constante do tipo string é igual ao número de caracteres escritos nela mais um (para o caractere nulo).

Como acontece com qualquer array em C, usar a constante do tipo string em uma expressão converte o array em um ponteiro (veja [_Ponteiros_](#user-content-fn-1)[^1]) para o elemento zero do array (veja [_Acessando Elementos de Arrays_](#user-content-fn-2)[^2]). Esse ponteiro terá o tipo `char *` porque aponta para um elemento do tipo `char`. `char *` é um exemplo de designador de tipo para um tipo de ponteiro (veja [_Designadores de Tipo para Ponteiros_](#user-content-fn-3)[^3]). Esse tipo é usado para strings em geral, não apenas para strings expressas como constantes em um programa.

Assim, a constante do tipo string `"Foo!"` é quase equivalente a declarar um array como este:

```c
char string_array_1[] = {'F', 'o', 'o', '!', '\0' };
```

E então usar `string_array_1` no programa. No entanto, existem duas diferenças:

1. A constante do tipo string não define um nome para o array.
2. A constante do tipo string provavelmente será armazenada em uma área de memória somente leitura.

Novas linhas não são permitidas no texto de uma constante do tipo string. O motivo para essa proibição é detectar o erro de omitir o ‘"’ de fechamento. Para inserir uma nova linha em uma constante do tipo string, escreva-a como ‘\n’ na constante do tipo string.

Um caractere nulo real no código fonte dentro de uma constante do tipo string gera um aviso (_warning_) do compilador. Para colocar um caractere nulo no meio de uma constante do tipo string, escreva ‘\0’ ou ‘\000’.

Constantes do tipo string consecutivas são efetivamente concatenadas. Assim,

```c
"Fo" "o!"   é equivalente a   "Foo!"
```

Isso é útil para escrever uma string que contém várias linhas, como esta:

```c
"Esta mensagem é tão longa que precisa de mais de\n"
"uma única linha de texto. C não permite que uma\n"
"nova linha se represente diretamente em uma\n"
"constante do tipo string, então precisamos escrever\n"
"\\n para colocá-la na string. Para melhorar a\n"
"legibilidade do código-fonte, é recomendável\n"
"inserir quebras de linha no código onde elas\n"
"ocorrem no conteúdo da constante.\n"
```

A sequência de uma barra invertida e uma nova linha é ignorada em qualquer lugar de um programa C, inclusive dentro de uma constante do tipo string. Assim, você pode escrever constantes do tipo string em várias linhas desta forma:

```c
"Esta é outra maneira de inserir novas linhas em uma\n\
constante do tipo string e quebrar a linha depois delas\n\
no código-fonte."
```

No entanto, a concatenação é a forma recomendada de fazer isso.

Você também pode escrever constantes do tipo string "estranhas" como esta:

```c
"Fo\
o!"
```

Mas não faça isso—escreva assim:

```c
"Foo!"
```

Tome cuidado para não passar uma constante do tipo string para uma função que modifica a string recebida. A memória onde a constante do tipo string está armazenada pode ser somente leitura, o que causaria um sinal fatal SIGSEGV, normalmente terminando a função (veja [_Sinais_](#user-content-fn-4)[^4]). Ainda pior, a memória pode não ser somente leitura. Nesse caso, a função poderia modificar a constante do tipo string, prejudicando o conteúdo de outras constantes do tipo string que deveriam conter o mesmo valor e foram unificadas pelo compilador.

[^1]: Pendente de tradução

[^2]: Pendente de tradução

[^3]: Pendente de tradução

[^4]: Pendente de tradução
