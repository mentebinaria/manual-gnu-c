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

# Imprimindo Ponteiros

Para imprimir o **valor numérico de um ponteiro**, use o especificador de formato **`%p`**. Por exemplo:

```c
void
print_pointer(void *ptr)
{
  printf("Pointer value is %p\n", ptr);
}
```

O especificador `%p` funciona com **qualquer tipo de ponteiro**. Ele imprime `0x` seguido do **endereço em hexadecimal**, usando o tipo inteiro sem sinal apropriado.
