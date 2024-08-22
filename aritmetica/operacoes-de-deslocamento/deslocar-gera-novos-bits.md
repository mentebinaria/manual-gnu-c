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

# Deslocar Gera Novos Bits

Uma operação de deslocamento move os bits para uma extremidade do número e precisa gerar novos bits na outra extremidade.

Deslocar para a esquerda um bit deve gerar um novo bit menos significativo. Ele sempre insere um zero ali. Isso é equivalente a multiplicar pela potência de 2 correspondente. Por exemplo,

```c
5 << 3     é equivalente a   5 * 2*2*2
-10 << 4   é equivalente a   -10 * 2*2*2*2
```

O significado de deslocar para a direita depende se o tipo de dado é com sinal ou sem sinal (veja [Tipos Com ou Sem Sinal](#user-content-fn-1)[^1]). Para um tipo de dado com sinal, ele realiza um “deslocamento aritmético,” que mantém o sinal do número inalterado ao duplicar o bit de sinal. Para um tipo de dado sem sinal, ele realiza um “deslocamento lógico,” que sempre insere zeros no bit mais significativo.

Em ambos os casos, deslocar para a direita um bit é uma divisão por dois, arredondando em direção ao infinito negativo. Por exemplo,

```c
(unsigned) 19 >> 2 ⇒ 4
(unsigned) 20 >> 2 ⇒ 5
(unsigned) 21 >> 2 ⇒ 5
```

Para um operando esquerdo negativo `a`, `a >> 1` não é equivalente a `a / 2`. Ambos dividem por 2, mas `‘/’` arredonda em direção a zero.

A contagem de deslocamento deve ser zero ou maior. Deslocar por um número negativo de bits produz resultados dependentes da máquina.

[^1]: Capítulo pendente de tradução
