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

# Constantes do Tipo String Larga

Uma constante do tipo string larga (_wide string_) representa um array de caracteres de 16 bits ou 32 bits. Elas são raramente usadas; se você está apenas aprendendo C, pode ignorar esta seção.

Existem três tipos de constantes do tipo string larga, que diferem no tipo de dado usado para cada caractere na string. Cada constante desse tipo é equivalente a um array de números inteiros, mas o tipo desses inteiros depende do tipo específico da constante. Quando utilizada em uma expressão, a constante será convertida em um ponteiro para o primeiro elemento do array, como ocorre normalmente com arrays em C (veja [_Acessando Elementos de um Array_](#user-content-fn-1)[^1]). Para cada tipo de constante do tipo string larga, indicamos aqui o tipo desse ponteiro.

**`char16_t`**\
Este é um tipo de constante do tipo string Unicode de 16 bits: cada elemento é um código de caractere Unicode de 16 bits com o tipo `char16_t`, de forma que a string possui o tipo de ponteiro `char16_t *`. (Este é um designador de tipo; veja [_Designadores de Tipo para Ponteiros_](#user-content-fn-2)[^2].) A constante é escrita como ‘u’ (em letra minúscula) seguida (sem espaço intermediário) de uma constante do tipo string com a sintaxe usual.

**`char32_t`**\
Este é um tipo de constante do tipo string Unicode de 32 bits: cada elemento é um código de caractere Unicode de 32 bits, e a string possui o tipo `char32_t *`. A constante é escrita como ‘U’ (em letra maiúscula) seguida (sem espaço intermediário) de uma constante do tipo string com a sintaxe usual.

**`wchar_t`**\
Este é o tipo original de constante do tipo string larga. A constante é escrita como ‘L’ (em letra maiúscula) seguida (sem espaço intermediário) de uma constante do tipo string com a sintaxe usual, e a string possui o tipo `wchar_t *`.

A largura do tipo de dado `wchar_t` depende da plataforma de destino, o que torna esse tipo de string larga um pouco menos útil em comparação com os tipos mais novos.

{% hint style="info" %}
No Windows, por padrão, as funções da API que operam com strings requerem strings largas. Por exemplo:&#x20;

`MessageBox(NULL, L"Olá", L"Mundo", MB_OK)` .
{% endhint %}

Os tipos `char16_t` e `char32_t` são declarados no cabeçalho `uchar.h`. O tipo `wchar_t` é declarado no cabeçalho `stddef.h`.

Constantes consecutivas do tipo string larga do mesmo tipo se concatenam, assim como constantes do tipo string comuns. Uma constante do tipo string larga concatenada com uma constante do tipo string comum resulta em uma constante do tipo string larga. No entanto, não é possível concatenar duas constantes do tipo string larga de tipos diferentes. Além disso, não é possível concatenar uma constante do tipo string larga (de qualquer tipo) com uma constante do tipo string UTF-8.

[^1]: Pendente de tradução

[^2]: Pendente de tradução
