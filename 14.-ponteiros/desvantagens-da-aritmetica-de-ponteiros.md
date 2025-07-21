---
layout:
  width: default
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
  metadata:
    visible: true
---

# Desvantagens da Aritmética de Ponteiros

A aritmética de ponteiros é uma construção **limpa e elegante**, mas também é a **causa de uma das principais falhas de segurança** na linguagem C.

**Teoricamente**, só é válido ajustar um ponteiro dentro de **um único objeto alocado como unidade** na memória. No entanto, se você **ajustar acidentalmente** um ponteiro além dos limites desse objeto e ele invadir outro objeto, o sistema **não tem como detectar esse erro**.

Um bug desse tipo pode facilmente causar **sobrescrita indesejada** (_clobbering_) de parte de outro objeto. Por exemplo, com `array[-1]`, você pode **ler ou escrever fora dos limites** do array — provavelmente acessando parte de **outros dados**.

***

Ao combinar **aritmética de ponteiros** com **conversões entre tipos de ponteiros**, é possível criar um ponteiro com **alinhamento incorreto** para seu tipo. Veja o exemplo:

```c
int a[2];
char *pa = (char *)a;
int *p = (int *)(pa + 1);
```

Aqui, `p` passa a apontar para um “int” que inclui parte de `a[0]` e parte de `a[1]`. Tentar desreferenciar isso com `*p` pode:

* causar um **sinal fatal** `SIGSEGV` (veja _Sinais_);
* ou retornar o conteúdo desse `int` desalinhado.

Mesmo que “funcione”, isso pode ser **bem lento**. Também pode causar **confusão de aliasing** (veja [_Aliasing_](#user-content-fn-1)[^1]), isto é, **interpretação ambígua** de qual valor é lido ou escrito.

{% hint style="danger" %}
Usar ponteiros com alinhamento incorreto é arriscado — não faça isso, a menos que seja realmente necessário.
{% endhint %}

[^1]: Apêndice pendente de tradução
