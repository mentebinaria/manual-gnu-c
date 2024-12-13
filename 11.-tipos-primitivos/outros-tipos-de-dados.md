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

# Outros Tipos de Dados

Além dos tipos primitivos, C oferece várias formas de construir novos tipos de dados. Por exemplo:

* Você pode definir **ponteiros**, valores que representam os endereços de outros dados (veja [_Ponteiros_](#user-content-fn-1)[^1]).
* Pode definir **estruturas**, como em muitas outras linguagens (veja [_Estruturas_](#user-content-fn-2)[^2]).
* Pode criar **uniões**, que definem múltiplas formas de interpretar o conteúdo do mesmo espaço de memória (veja [_Uniões_](#user-content-fn-3)[^3]).
* **Enumerações** são coleções de códigos inteiros nomeados (veja [_Tipos de Enumeração_](#user-content-fn-4)[^4]).

Os tipos de **arrays** em C são usados para alocar espaço para objetos, mas C não permite operar sobre um valor de array como um todo. Veja [_Arrays_](#user-content-fn-5)[^5].

{% hint style="info" %}
O último parágrafo explica que não podemos fazer coisas como `int array[] = 10` em C (não conheço linguagem que permita operar arrays assim). Por serem conjunto de dados, é preciso operar sobre seus elementos, por exemplo, `array[0] = 10`.
{% endhint %}



[^1]: Pendente de tradução

[^2]: Pendente de tradução

[^3]: Pendente de tradução

[^4]: Pendente de tradução

[^5]: Pendente de tradução
