# 👉 14. Ponteiros

Entre as linguagens de alto nível, C é relativamente de baixo nível, próxima da máquina. Isso se deve principalmente ao fato de possuir ponteiros explícitos. Um valor de um ponteiro é um endereço numérico de dados na memória. O tipo de dado a ser encontrado nesse endereço é especificado pelo tipo de dado do próprio ponteiro. Nada na linguage C pode determinar o tipo de dado “correto” da informação na memória; ela segue cegamente o tipo de dado do ponteiro usado para acessar os dados.

O operador unário ‘\*’ obtém os dados para os quais um ponteiro aponta — isso é chamado de desreferenciar o ponteiro. Seu valor sempre possui o tipo que o ponteiro aponta.

C também permite ponteiros para funções, mas como há algumas diferenças em seu funcionamento, trataremos deles mais adiante. [Veja Ponteiros para Funções](#user-content-fn-1)[^1].

[^1]: Capítulo pendente de tradução
