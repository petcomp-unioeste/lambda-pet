# Projeto de implementação de uma interpretador de brainfuck

Realizado nos encontros 3, 4 e 5


# O que é brainfuck

  * "Brainfuck is an esoteric programming language created in 1993 by
    Urban Müller, and is notable for its extreme minimalism. The
    language consists of only eight simple commands and an instruction
    pointer. While it is fully Turing complete, it is not intended for
    practical use, but to challenge and amuse programmers. Brainfuck
    simply requires one to break commands into microscopic steps".

    [source](https://en.wikipedia.org/wiki/Brainfuck "brain-fuck wikipedia")

| character | o que faz                                                 |
|:---------:|-----------------------------------------------------------|
| +         | Incrementa o charactere na posição atual do ponteiro      |
| -         | Decrementa o charactere na posição atual do ponteiro      |
| <         | Move o ponteiro para a esqurda na fita                    |
| >         | Move o ponteiro para a direita na fita                    |
| ,         | Lê um char e o escreve na posição atual do ponteiro       |
| .         | Print o char na posição atual do ponterio                 |
| [         | Se o charactere da fita for igual a zero avance até ]     |
| ]         | Se o charactere da fita for diferente de zero volte até [ |

---

# Parte 1: Parsing the brain-fuck.

  * Vamos iniciar o projeto lendo uma string de characteres e
    eliminado os characteres que não pertencem ao brainfuck. Programas
    em brainfuck consistem de string de characteres, sendo que cada
    charactere é uma instrução. Strings podem ser consideradas listas
    de characteres e felizmente scheme tem uma função que facilita
    nossa vida. 'string->list' recebe como parâmetro uma string e
    retorna uma lista contendo todos os characteres da string.

```scheme
(string->list "uma string")
```

  * Nota: Characteres em scheme são denotados como: '#\a' que denota
    'a'.

  * Criaremos uma função chamada 'bf-filter' que recebe como
    parâmetro um charactere e retorna true se este prertence ao
    conjunto de caracteres do brainfuck.

```scheme
(define (bf-filter tkn)
  (cond
   ((equal? tkn #\+) #t)
   ((equal? tkn #\-) #t)
   ((equal? tkn #\.) #t)
   ((equal? tkn #\,) #t)
   ((equal? tkn #\<) #t)
   ((equal? tkn #\>) #t)
   ((equal? tkn #\[) #t)
   ((equal? tkn #\]) #t)
   (else #f)))
```

  * Agora podemos mapear 'bf-filter' sobre a lista de characteres do
    programa em brainfuck e coletar apenas os characteres que de fato
    pertencem a linguagem.

```scheme
(filter bf-filter (string->list "+++++++---ddlksaj------"))
```

  * O resultado disto é um lista de characteres que contém apenas o
    que queremos.

---

# Parte 2: Modeling the state.

  * TODO:

---

# Parte 3: Brain-fuck as functions.

  * TODO:

---

# Parte 4: Loop.

  * TODO:
