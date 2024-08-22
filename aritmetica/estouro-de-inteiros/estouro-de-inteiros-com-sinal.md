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

# Estouro com Inteiros com Sinal

Para inteiros com sinal, o resultado de um estouro em C é, em princípio, indefinido, o que significa que qualquer coisa pode acontecer. Portanto, compiladores C podem fazer otimizações que tratam o caso de estouro sem qualquer preocupação. (Como o resultado do estouro é indefinido em princípio, não se pode alegar que essas otimizações são errôneas.)

**Cuidado:** Essas otimizações podem fazer coisas surpreendentes. Por exemplo,

```c
int i;
…
if (i < i + 1)
  x = 5;
```

poderia ser otimizado para fazer a atribuição incondicionalmente, porque a condição `if` é sempre verdadeira se `i + 1` não causar estouro.

O GCC oferece opções do compilador para controlar o tratamento de estouro de inteiros com sinal. Essas opções operam por módulo; ou seja, cada módulo se comporta de acordo com as opções com as quais foi compilado.

Essas duas opções especificam maneiras particulares de lidar com estouro de inteiros com sinal, além da maneira padrão:

`-fwrapv` Faz com que operações de inteiros com sinal sejam bem definidas, como operações de inteiros sem sinal: elas produzem os n bits menos significativos do resultado real. O mais alto desses n bits é o bit de sinal do resultado. Com `-fwrapv`, essas operações fora do intervalo não são consideradas estouro, então (estritamente falando) o estouro de inteiros nunca acontece.

A opção `-fwrapv` habilita algumas otimizações com base nos valores definidos de resultados fora do intervalo. No GCC 8, ela desabilita otimizações que se baseiam em assumir que operações de inteiros com sinal não causarão estouro.

`-ftrapv` Gera um sinal SIGFPE quando ocorre estouro de inteiros com sinal. Isso termina o programa, a menos que o programa lide com o sinal. Veja Sinais[^1].

Outra opção útil para encontrar onde ocorre estouro é:

`-fsanitize=signed-integer-overflow` Exibe uma mensagem de aviso em tempo de execução quando ocorre estouro de inteiros com sinal. Isso verifica os operadores ‘+’, ‘\*’ e ‘-’. Isso tem prioridade sobre `-ftrapv`.

[^1]: Capítulo pendente de tradução
