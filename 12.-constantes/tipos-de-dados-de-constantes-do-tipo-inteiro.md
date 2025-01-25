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

# Tipos de Dados de Constantes do Tipo Inteiro

O tipo de uma constante do tipo inteiro é normalmente `int`, se o valor couber nesse tipo, mas aqui estão as regras completas. O tipo de uma constante do tipo inteiro é o primeiro nesta sequência que pode representar corretamente o valor:

* `int`
* `unsigned int`
* `long int`
* `unsigned long int`
* `long long int`
* `unsigned long long int`

E que não seja excluído pelas regras a seguir:

* Se a constante tiver o sufixo ‘l’ ou ‘L’, isso exclui os dois primeiros tipos (não longos).
* Se a constante tiver o sufixo ‘ll’ ou ‘LL’, isso exclui os primeiros quatro tipos (não long long).
* Se a constante tiver o sufixo ‘u’ ou ‘U’, isso exclui os tipos com sinal.
* Caso contrário, se a constante for decimal (não binária, octal ou hexadecimal), isso exclui os tipos sem sinal.

**Exemplos de Sufixos:**

```c
3000000000u      // três bilhões como unsigned int.
0LL              // zero como long long int.
0403l            // 259 como long int.
```

Os sufixos em constantes do tipo inteiro são raramente usados. Quando o tipo preciso é importante, é mais claro converter explicitamente (veja _Conversão de Tipo Explícita_).

Veja [_Tipos de Dados Inteiros_](../11.-tipos-primitivos/tipos-de-dados-inteiros/).
