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

# Operações Bit-a-bit

Operadores bit-a-bit (_bitwise_, em inglês) operam em inteiros, tratando cada bit de forma independente. Eles não são permitidos para tipos de ponto flutuante.

Os exemplos nesta seção usam constantes binárias, começando com ‘0b’ (veja [Constantes Inteiras](#user-content-fn-1)[^1]). Elas representam inteiros de 32 bits do tipo `int`. Vamos aos operadores:

### Negação

```c
~a
```

Operador unário para negação bitwise; este operador altera cada bit de `a` de 1 para 0 ou de 0 para 1.

```c
~0b10101000 ⇒ 0b11111111111111111111111101010111
~0 ⇒ 0b11111111111111111111111111111111
~0b11111111111111111111111111111111 ⇒ 0
~ (-1) ⇒ 0
```

É útil lembrar que `~x + 1` é igual a `-x`, para inteiros, e `~x` é igual a `-x - 1`. O último exemplo acima mostra isso com `-1` como `x`.

### Conjunção (E / AND)

```c
a & b
```

Operador binário para “and” bit-a-bit ou “conjunção”. Cada bit no resultado é 1 se esse bit for 1 em ambos `a` e `b`.

```c
0b10101010 & 0b11001100 ⇒ 0b10001000
```

### Disjunção (OU / OR)

```c
a | b
```

Operador binário para “ou” bit-a-bit (“ou inclusivo” ou “disjunção”). Cada bit no resultado é 1 se esse bit for 1 em `a` ou `b`.

```c
0b10101010 | 0b11001100 ⇒ 0b11101110
```

### Ou Exclusivo (XOR)

```c
a ^ b
```

Operador binário para “xor” bit-a-bit (“ou exclusivo”). Cada bit no resultado é 1 se esse bit for 1 em exatamente um de `a` e `b`.

```c
0b10101010 ^ 0b11001100 ⇒ 0b01100110
```

Para entender o efeito desses operadores em inteiros com sinal, lembre-se de que todos os computadores modernos usam representação em complemento de dois (veja [Representações de Inteiros](#user-content-fn-2)[^2]) para inteiros negativos. Isso significa que o bit mais alto do número indica o sinal; ele é 1 para um número negativo e 0 para um número positivo. Em um número negativo, o valor nos outros bits aumenta à medida que o número se aproxima de zero, de modo que `0b111…111` é -1 e `0b100…000` é o inteiro negativo mais baixo possível.

**Aviso:** C define uma ordem de precedência para os operadores binários bit-a-bit, mas você nunca deve confiar nisso. Você nunca deve confiar em como os operadores binários bit-a-bit se relacionam em precedência com os operadores binários aritméticos e de deslocamento. Outros programadores não lembram dessa ordem de precedência, então sempre use parênteses para especificar explicitamente o aninhamento.

Por exemplo, suponha que `offset` seja um inteiro que especifica o deslocamento dentro da memória compartilhada de uma tabela, exceto que seus poucos bits inferiores (LOWBITS indica quantos) são flags especiais. Veja como obter apenas esse deslocamento e adicioná-lo ao endereço base.

```c
shared_mem_base + (offset & (-1 << LOWBITS))
```

Graças ao conjunto externo de parênteses, não precisamos saber se ‘&’ tem precedência mais alta que ‘+’. Graças ao conjunto interno, não precisamos saber se ‘&’ tem precedência mais alta que ‘<<’. Mas podemos confiar que todos os operadores unários têm precedência mais alta que qualquer operador binário, então não precisamos de parênteses ao redor do operando esquerdo de ‘<<’.

{% embed url="https://www.youtube.com/watch?v=BpPHV5mR6lg" %}



[^1]: Capítulo pendente de tradução

[^2]: Capítulo pendente de tradução
