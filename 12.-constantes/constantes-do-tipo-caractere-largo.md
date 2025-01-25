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

# Constantes do Tipo Caractere Largo

Uma constante do tipo caractere largo (_wide char_) representa caracteres com mais de 8 bits no código do caractere. Esta é uma funcionalidade pouco comum que precisamos documentar, mas que provavelmente você nunca usará. Se você está apenas aprendendo C, pode ignorar esta seção.

A constante original do tipo caractere largo em C é escrita como ‘L’ (maiúscula!) seguida imediatamente por uma constante de caractere comum (sem espaço intermediário). Seu tipo de dado é `wchar_t`, que é um alias definido em `stddef.h` para um dos tipos de inteiro padrão. Dependendo da plataforma, pode ser de 16 bits ou 32 bits. Se for de 16 bits, essas constantes de caractere usam a forma UTF-16 do Unicode; se forem de 32 bits, usam o UTF-32.

Também existem constantes Unicode do tipo caractere largo que especificam explicitamente a largura. Essas constantes começam com ‘u’ ou ‘U’ em vez de ‘L’. O prefixo ‘u’ especifica uma constante Unicode de 16 bits, e o prefixo ‘U’ especifica uma constante Unicode de 32 bits. Seus tipos são, respectivamente, `char16_t` e `char32_t`; esses tipos são declarados no arquivo de cabeçalho `uchar.h`. Essas constantes de caractere são válidas mesmo se `uchar.h` não for incluído, mas alguns usos podem ser inconvenientes sem incluir o cabeçalho para declarar esses nomes de tipo.

O caractere representado em uma constante do tipo caractere largo pode ser um caractere ASCII comum. `L'a'`, `u'a'` e `U'a'` são todos válidos e todos iguais a `'a'`.

Em todos os três tipos de constantes do tipo caractere largo, você pode escrever diretamente um caractere Unicode não ASCII na constante; o valor da constante será o código Unicode do caractere. Ou você pode especificar o caractere Unicode com uma sequência de escape (veja [_Códigos de Caracteres Unicode_](codigos-de-caracteres-unicode.md)).
