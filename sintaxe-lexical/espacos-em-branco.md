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

# Espaços em Branco

O espaço em branco refere-se a caracteres que existem em um arquivo, mas aparecem em branco em uma impressão deste arquivo (ou tradicionalmente apareciam em branco, várias décadas atrás). A linguagem C exige espaço em branco para separar dois identificadores consecutivos ou para separar um identificador de uma constante numérica. Além disso, em algumas situações especiais descritas mais adiante, o espaço em branco é opcional; você pode usá-lo quando quiser, para tornar o código mais fácil de ler.

Espaço e tabulação (caractere "tab") no código C são tratados como caracteres de espaço em branco. Quebras de linha também são. Você pode representar uma quebra de linha com o caractere de nova linha (também chamado de linefeed ou LF), CR (carriage return), ou a sequência CRLF (dois caracteres: carriage return seguido de um caractere de nova linha).

O caractere de avanço de formulário (formfeed), Control-L, era tradicionalmente usado para dividir um arquivo em páginas. Ele ainda é usado dessa forma no código fonte, e as ferramentas que geram impressões agradáveis do código fonte ainda iniciam uma nova página após cada caractere de "formfeed". Dividir o código em páginas separadas por caracteres de avanço de formulário é uma boa maneira de dividi-lo em partes compreensíveis e mostrar a outros programadores onde começam e terminam.

O caractere de tabulação vertical, Control-K, era tradicionalmente usado para fazer a impressão avançar para a próxima seção de uma página. Não conhecemos nenhum motivo particular para usá-lo no código fonte, mas ele ainda é aceito como espaço em branco em C.

Comentários também são sintaticamente equivalentes ao espaço em branco.
