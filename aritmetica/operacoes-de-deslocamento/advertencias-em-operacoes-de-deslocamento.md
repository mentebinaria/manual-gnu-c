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

# Advertências em Operações de Deslocamento

**Aviso:** Se a contagem de deslocamento for maior ou igual à largura em bits do primeiro operando promovido, os resultados dependem da máquina. Logicamente falando, o valor "correto" seria -1 (para deslocamento à direita de um número negativo) ou 0 (em todos os outros casos), mas o resultado real é o que a instrução de deslocamento da máquina faz nesse caso. Portanto, a menos que você possa provar que o segundo operando não é grande demais, escreva código para verificá-lo em tempo de execução.

**Aviso:** Nunca confie na relação entre os operadores de deslocamento e outros operadores binários aritméticos em termos de precedência. Programadores não lembram dessas precedências e não entenderão o código. Sempre use parênteses para especificar explicitamente o aninhamento, assim:

```c
a + (b << 5)   /* Desloca primeiro, depois soma.  */
(a + b) << 5   /* Soma primeiro, depois desloca.  */
```

**Nota:** De acordo com o padrão C, o deslocamento de valores com sinal não é garantido para funcionar corretamente quando o valor deslocado é negativo ou se torna negativo durante a operação de deslocamento à esquerda. No entanto, apenas as pessoas mais rigorosas teriam motivo para se preocupar com isso; apenas computadores com instruções de deslocamento estranhas poderiam, plausivelmente, fazer isso de forma incorreta. No GNU C, a operação sempre funciona como esperado.
