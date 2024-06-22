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

# Compilando o Programa de Exemplo

Rodar um programa em C requer converter seu código-fonte num _arquivo executável_. Isto é chamado de compilar o programa, e o comando para fazer isso usando GNU C é o `gcc`.

O programa de exemplo consiste num único arquivo de código-fonte. Se o chamarmos de `fib1.c`, o comando completo para compilá-lo será:

```
gcc -g -O -o fib1 fib1.c
```

No comando acima, `-g` instrui que sejam geradas informações de depuração, `-O` diz para otimizar em níevel básico e `-o fib1` diz para criar o programa executável num arquivo `fib1`.

Para rodar o programa, use o nome do arquivo como um comando do shell. Por exemplo,

```
./fib1
```

Todavia, a menos que você tenha certeza de que o programa está correto, você deve esperar que precise depurá-lo. Portanto, use o comando

```
gdb fib1
```

que inicia o debugger (ou depurador) GDB (veja [A Sample GDB Session](https://sourceware.org/gdb/current/onlinedocs/gdb/Sample-Session.html#Sample-Session) em _Debugging with GDB_) e você pode rodar e depurar o programa executável `fib1`.

Um conselho do Richard Stallman, a partir da sua experiência pessoal, é ir para o debugger assim que você conseguir reproduzir o problema. Não tente evitar isso usando outros métodos—ocasionalmente eles funcionam como atalhos, mas normalmente eles levam muito tempo. Com o debugger você certamente vai encontrar o problema num tempo razoável; em geral, você terminará seu trabalho mais rapidamente. Quanto mais cedo você levar a sério e iniciar o debugger, mais cedo provavelmente encontrará o problema.

Veja Compilação para uma introdução sobre compilação de programais mais complexos que consistem em mais de um arquivo de código-fonte.
