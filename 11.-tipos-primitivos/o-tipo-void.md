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

# O Tipo Void



O tipo de dado `void` é um tipo fictício — ele não permite operações. Ele literalmente significa “nenhum valor”. Quando uma função não deve retornar nenhum valor, usamos `void` como seu tipo de retorno. Nesse caso, as instruções `return` nessa função não devem especificar nenhum valor (veja [_Instrução Return_](#user-content-fn-1)[^1]). Aqui está um exemplo:

```c
void
print_if_positive (double x, double y)
{
  if (x <= 0)
    return;
  if (y <= 0)
    return;
  printf ("Next point is (%f,%f)\n", x, y);
}
```

Uma função que retorna `void` é comparável ao que outras linguagens (por exemplo, Fortran e Pascal) chamam de "procedimento" ao invés vez de "função".

[^1]: Pendente de tradução
