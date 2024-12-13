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

# Tipos de Dados Complexos

Números complexos podem incluir uma parte real e uma parte imaginária. As constantes numéricas abordadas anteriormente possuem valores reais. Uma constante com valor imaginário é uma constante numérica real comum seguida de ‘i’.

Para declarar variáveis numéricas como complexas, use a palavra-chave `_Complex`. Os tipos de dados complexos padrão em C são de ponto flutuante:

```c
_Complex float foo;
_Complex double bar;
_Complex long double quux;
```

No entanto, o GNU C também oferece suporte a tipos inteiros complexos.

Como `_Complex` é uma palavra-chave assim como `float`, `double` e `long`, essas palavras-chave podem aparecer em qualquer ordem, mas a ordem mostrada acima parece ser a mais lógica.

O GNU C suporta constantes para valores complexos. Por exemplo, `4.0 + 3.0i` tem o valor `4 + 3i` com o tipo `_Complex double`. Veja _Constantes Imaginárias_.

Para extrair as partes real e imaginária de um número complexo, o GNU C fornece as palavras-chave `__real__` e `__imag__`:

```c
_Complex double foo = 4.0 + 3.0i;

double a = __real__ foo; /* a agora é 4.0. */
double b = __imag__ foo; /* b agora é 3.0. */
```

O padrão C não inclui essas palavras-chave e, em vez disso, depende de funções definidas em `complex.h` para acessar as partes real e imaginária de um número complexo: `crealf`, `creal` e `creall` extraem a parte real de um número complexo de tipo `float`, `double` ou `long double`, respectivamente; `cimagf`, `cimag` e `cimagl` extraem a parte imaginária.

O GNU C também define ‘\~’ como um operador para a conjugação complexa, o que significa negar a parte imaginária de um número complexo:

```c
_Complex double foo = 4.0 + 3.0i;
_Complex double bar = ~foo; /* bar agora é 4 - 3i. */
```

Para compatibilidade com o padrão C, você pode usar a função de biblioteca apropriada: `conjf`, `conj` ou `conjl`.

***

**Nota de compatibilidade:**\
Para compatibilidade com versões mais antigas do GNU C, a palavra-chave `__complex__` também é aceita. No entanto, para usar um recurso mais novo, use a nova palavra-chave `_Complex`, conforme definido na ISO C11.
