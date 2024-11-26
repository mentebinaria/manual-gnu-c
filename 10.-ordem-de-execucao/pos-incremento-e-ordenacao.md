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

# Pós-incremento e Ordenação

Os requisitos de ordenação para as operações de pós-incremento e pós-decremento (veja [Pós-incremento e Pós-decremento](../7.-expressoes-de-atribuicao/pos-incremento-e-pos-decremento.md)) são flexíveis: esses efeitos colaterais devem ocorrer "um pouco depois," antes do próximo ponto de sequência. Isso ainda permite várias ordens que podem produzir resultados diferentes. Nesta expressão:

```c
z = x++ - foo ()
```

não é previsível se `x` será incrementado antes ou depois de chamar a função `foo`. Se `foo` referir-se a `x`, ela pode ver o valor antigo ou o valor incrementado.

{% hint style="info" %}
A solução para estes e outros problemas de ordem de execução é simples: definir bem os pontos de sequência ao usar instruções separadas. Por exemplo:&#x20;

`x++;`

`z = x - foo ();`
{% endhint %}

Nesta expressão em particular:

```c
x = x++
```

`x` certamente será incrementado, mas o valor incrementado pode ser substituído pelo valor antigo. Isso acontece porque a incrementação e a atribuição podem ocorrer em qualquer ordem. Se a incrementação de `x` ocorrer depois da atribuição para `x`, o valor incrementado permanecerá. Mas, se a incrementação ocorrer primeiro, a atribuição colocará o valor não incrementado de volta em `x`, deixando a expressão como um todo sem alterar o valor de `x`.

**Conclusão**: evite tais expressões. Certifique-se, ao usar pós-incremento e pós-decremento, de que a expressão específica que você utiliza não seja ambígua quanto à ordenação de execução.
