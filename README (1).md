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

# Prefácio

Este manual explica a linguagem C para uso com o GNU Compiler Collection (GCC) em sistema operacional GNU/Linux e em outros sistemas. Nós nos referimos a este dialeto como GNU C. Se você já sabe C, pode usar este manual como referência.

Se você sabe conceitos básicos de programação mas não sabe nada sobre C, você pode ler este manual sequencialmente desde o início para aprender a linguagem C.

Se você é iniciante em programação, recomendamos que você primeiro aprenda uma linguagem com coleta de lixo automática e sem ponteiros explícitos ao invés de começar com C. Boas opções incluem Lisp, Scheme, Python e Java. Por conta dos ponteiros explícitos da linguagem C, quem programa precisa ter cuidado para evitar certos tipos de erro ao utilizar a memória.

C é uma linguagem venerável; ela foi usada pela primeira vez em 1973. O GNU C Compiler, posteriormente ampliado a GNU Compiler Collection, foi lançado pela primeira vez em 1987. Outras importantes linguagens de programação foram desenhadas com base no C: uma vez que você saiba C, ele te dá uma base útil para aprender C++, C#, Java, Scala, D, Go e outras.

A vantagem especial de C é que ele ao mesmo tempo é simples e te dá um acesso próximo ao hardware do computador, o que anteriormente requeria escrever código em linguagem assembler para descrever instruções de máquina individuais. Algumas pessoas chamaram o C de "uma linguagem assembler de alto nível" por conta de seus ponteiros explícitos e a falta de gerenciamento automático de memória. Como disse alguém brincando, "C combina o poder da linguagem assembler com a conveniência da linguagem assembler". Todavia, C é muito mais portável e muito mais fácil de ler e de escrever que a linguagem assembler.

{% hint style="info" %}
O livro chama de **linguagem assembler** o que normalmente no Brasil nos referimos como linguagem **Assembly**. Há pessoas que defendem que **assembler** é o compilador de Assembly, enquanto Assembly é a linguagem em si, mas no livro o autor chama a linguagem de assembler mesmo.
{% endhint %}

Este manual descreve a linguagem GNU C suportada pelo GNU Compiler Collection (GCC) desde 2017 aproximadamente. Por favor, nos informe se qualquer mudança for necessária para refletir a versão atual do GNU C.

Se uma determinada construção não estiver disponível ou funcionar de forma diferente em outros compiladores, nós avisaremos. Se uma construção não for parte do padrão ISO C, nós diremos que é uma "extensão GNU C", porque é útil que você saiba isso. Todavia, padrões e outros dialetos são tópicos secundários para este manual. Em razão da simplicidade, manteremos tais notas curtas, a menos que seja vital dizer mais sobre.

Alguns aspectos do significado de programas em C dependem da plataforma alvo: em qual computador e em qual o sistema operacional o código compilado vai rodar. Quando for este o caso, avisaremos também.

Raramente mencionamos C++ ou outras linguagens que o GCC suporta. Esperamos que este manual sirva de base para escrever manuais para estas linguagens, mas linguagens tão diferentes não podem compartilhar um manual comum.

A linguagem C não provê facilidades _built-in_ (não traz facilidades nativas) para realizar operações como entrada e saída, gerenciamento de memória, manipulação de strings e similares. Ao invés disso, essas facilidades são providas pelas funções definidas na biblioteca padrão, que está automaticamente disponível em qualquer programa em C. Veja A Biblioteca C Padrão no Manual de Referência da Biblioteca GNU C.

A maioria dos sistemas GNU/Linux usa a biblioteca GNU C (glibc) para prover tais funcionalidades. Ela mesma é escrita em C, então uma vez que você saiba C, pode ler o código-fonte dela e ver como as funções da biblioteca fazem seu trabalho. Uma fração das funções é implementada como chamadas de sistema (system calls), o que significa que elas contêm uma instrução especial que pede ao kernel (do Linux) para realizar uma tarefa específica. Para entender como elas são implementadas, você precisaria ler o código-fonte do Linux. Se uma função da biblioteca é uma chamada de sistema ou não, é um detalhe interno de implementação e não faz diferença para quem vai chamar a função.

Este manual incorpora o antigo Manual do Pré-processador GNU C, que foi um dos primeiros manuais GNU. Ele também usa textos to antigo Manual do GNU C que foi escrito por Trevis Rothwell e James Youngman.

O GNU C tem vários recursos obscuros, cada um disponível seja por retrocompatibilidade ou para atender situações muito específicas. Nós os colocamos num manual complementar, o Manual de Obscuridades do GNU C, que será publicado digitalmente no futuro.

Por favor, reporte erros e sugestões (em inglês) para c-manual@gnu.org. Para erros de tradução, reporte [aqui](https://www.mentebinaria.com.br/contact).
