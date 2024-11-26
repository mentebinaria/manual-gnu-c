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

# Atribuição Simples

Uma expressão de atribuição simples calcula o valor do operando à direita e o armazena no _lvalue_ à esquerda. Aqui está uma expressão de atribuição simples que armazena 5 em `i`:

```c
i = 5
```

Dizemos que isso é uma atribuição para a variável `i` e que atribui a `i` o valor 5. Não tem ponto e vírgula porque é uma expressão (portanto, tem um valor). Adicionar um ponto e vírgula no final a tornaria uma instrução (veja [_Instrução de Expressão_](#user-content-fn-1)[^1]).

Aqui está outro exemplo de uma expressão de atribuição simples. Seus operandos não são simples, mas o tipo de atribuição feita aqui é uma atribuição simples.

```c
x[foo ()] = y + 6
```

Uma atribuição simples com dois tipos de dados numéricos diferentes converte o valor do operando à direita para o tipo do _lvalue_, se possível. Ela pode converter qualquer tipo numérico para qualquer outro tipo numérico.

A atribuição simples também é permitida em alguns tipos não numéricos: ponteiros (veja [_Ponteiros_](#user-content-fn-2)[^2]), estruturas (veja [_Atribuição de Structs_](#user-content-fn-3)[^3]) e uniões (veja[ _Uniões_](#user-content-fn-4)[^4]).

Aviso: A atribuição não é permitida em arrays porque em C não existem valores de array; variáveis em C podem ser arrays, mas esses arrays não podem ser manipulados como um todo. Veja [Limitações de Arrays em C](#user-content-fn-5)[^5].

Veja [_Conversões de Tipos em Atribuições_](#user-content-fn-6)[^6] para as regras completas sobre tipos de dados usados em atribuições.

[^1]: Capítulo pendente de tradução

[^2]: Capítulo pendente de tradução

[^3]: Capítulo pendente de tradução

[^4]: Capítulo pendente de tradução

[^5]: Capítulo pendente de tradução

[^6]: Capítulo pendente de tradução
