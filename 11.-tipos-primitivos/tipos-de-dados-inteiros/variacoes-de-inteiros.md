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

# Variações de Inteiros

Os tipos inteiros em C têm nomes padrão, mas seu significado pode variar dependendo do tipo de plataforma usada: o tipo de computador, o sistema operacional e o compilador. Pode até mesmo depender das opções usadas no compilador.

O `char` simples pode ser **com sinal** ou **sem sinal**; isso também depende da plataforma. Mesmo no GNU C, não há uma regra geral.

Em teoria, os tamanhos de todos os tipos inteiros podem variar. `char` é sempre considerado um "byte" em C, mas não necessariamente um byte de 8 bits; em algumas plataformas, ele pode ter mais de 8 bits. O padrão ISO C especifica apenas que nenhum desses tipos pode ser mais estreito do que os que estão acima dele na lista de [_Inteiros Básicos_](inteiros-basicos.md) e que `short` tem pelo menos 16 bits.

É possível que no futuro o GNU C suporte plataformas onde `int` tenha 64 bits. Na prática, no entanto, nos computadores reais de hoje, há pouca variação; você pode confiar na tabela apresentada anteriormente (veja [_Inteiros Básicos_](inteiros-basicos.md)).

Para ter certeza absoluta do tamanho de um tipo inteiro, use os tipos `int16_t`, `int32_t` e `int64_t`. Seus tipos sem sinal correspondentes adicionam ‘u’ no início: `uint16_t`, `uint32_t` e `uint64_t`. Para definir todos esses tipos, inclua o arquivo de cabeçalho `stdint.h`.

O GNU C Compiler compila para alguns controladores embarcados que usam dois bytes para `int`. Em alguns, `int` é apenas um "byte", e o mesmo vale para `short int` — mas esse "byte" pode conter 16 bits ou até 32 bits. Esses processadores não suportam sistemas operacionais comuns (eles têm seus próprios sistemas operacionais especializados), e a maioria dos programas em C não tenta oferecer suporte a tais processadores.
