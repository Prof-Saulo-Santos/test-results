# UNIARA - UNIVERSIDADE DE ARARAQUARA
## Avaliação de Linguagem C
## Marque com um X: Algoritmos [  ] / Laboratório [  ]

**NOME COMPLETO EM LETRA DE FORMA:** ________________________________________________________________________________

**RA:** ____________________________________&nbsp;&nbsp;&nbsp; **Curso:** ___________________________________________

---

> **Instruções:**
> - Cada questão apresenta um programa C **completo e compilável**.
> - Analise o código **linha por linha** e escreva exatamente o que será impresso na tela.
> - Deixe seu celular desligado e no chão, embaixo de sua carteira a vista de todos. 
> - Responda no espaço indicado abaixo de cada questão.
> - **Valor:** cada questão vale **2,0 pontos** → Total: **10,0 pontos**

---

## Questão 1
```c
#include <stdio.h>

void questao1(char str[15], int *aux) {
    int i = 0;
    while (str[i] != '\0') i++;
    *aux = i;
}

int main() {
    char palavra[15] = "linguag3em";
    int temp;
    questao1(palavra, &temp);
    printf("Temp = %d\n", temp);
    return 0;
}
```

**O que será impresso?**

```
Esse programa em linguagem C calcula a quantidade de caracteres de uma string (a palavra "linguag3em").

Especificamente, o programa fará o seguinte:

Ele analisa a palavra "linguag3em".
Como "linguag3em" tem 10 letras/caracteres lidos até o caractere nulo, a função define a variável temp como 10.
O programa imprime o texto "Temp = 10" na tela.

Passo a passo de como o código funciona:
A função questao1:

Recebe uma string (str) e um ponteiro para um número inteiro (aux).
int i = 0;: Inicializa um contador em zero.
O laço while: Ele percorre cada caractere da string (str[i]) até encontrar o caractere nulo ('\0'), incrementando i++ a cada passo (i = 10 no final).
*aux = i;: Atribui o número de caracteres contados à variável passada por referência (temp apontado em main).

Na função main:

É criada a variável palavra[15] contendo a palavra "linguag3em".
É passada a palavra e o endereço da variável temp para a função questao1.
Como "linguag3em" tem 10 caracteres lidos, a função termina com *aux = 10 sendo guardado em temp.
O printf então imprime "Temp = 10" no terminal.

Se você mudasse a palavra para "oi", por exemplo, o programa imprimiria "Temp = 2".
```

---

## Questão 2
```c
#include <stdio.h>

void questao2(char str[50]) {
    int leitura = 0, escrita = 0;
    while (str[leitura] != '\0') {
        if (str[leitura] != ' ') {
            str[escrita] = str[leitura];
            escrita++;
        }
        leitura++;
    }
    str[escrita] = '\0';
}

int main() {
    char frase[50] = "26 de marco de 2026";
    questao2(frase);
    printf("%s", frase);
    return 0;
}
```

**O que será impresso?**

```
Esse programa em linguagem C remove todos os espaços em branco de uma string (ou seja, ele junta todas as palavras de uma frase, como "26 de marco de 2026").

Especificamente, o programa fará o seguinte:

Ele analisa a frase "26 de marco de 2026".
Como ele copia apenas os caracteres que não são espaços, a frase é reescrita para "26demarcode2026".
O programa imprime o texto "26demarcode2026" na tela.

Passo a passo de como o código funciona:
A função questao2:

Recebe uma string (str).
int leitura = 0, escrita = 0;: Inicializa dois índices: um para ler os caracteres atuais (leitura) e o outro de escrita para repovoar os registros.
O laço while: Ele percorre cada caractere da string original (str[leitura]) até encontrar o caractere nulo ('\0').
A condição if (str[leitura] != ' '): Se o caractere não for um espaço (' '), ele o copia para si em str[escrita]. Em seguida, incrementa o índice de escrita. O lado do leitura++ cresce livremente pra ver todos à frente.
str[escrita] = '\0';: Após processar a união, finaliza com nulo e tranca a string.

Na função main:

É criada a variável frase[50] contendo o texto "26 de marco de 2026".
É passada a frase para a função questao2 e é modificada em ponteiro lá.
Após ver a compactação de 4 espaços, a escrita final ficará "26demarcode2026".
O printf então imprime a string comprimida: 26demarcode2026 no terminal.

Se você mudasse o texto para "boa prova", por exemplo, o programa imprimiria "boaprova".
```

---

## Questão 3

```c
#include <stdio.h>
#include <string.h>

void questao3(char str[6], int *resultado) {
    int n = strlen(str);
    *resultado = 1;
    for (int i = 0; i < n / 2; i++) {
        if (str[i] != str[n - 1 - i]) {
            *resultado = 0;
            break;
        }
    }
}

int main() {
    char palavra1[6] = "radar";
    int r1;
    questao3(palavra1, &r1);
    printf("%d",r1);
    return 0;
}
```

**O que será impresso?**

```
Esse programa em linguagem C verifica se uma palavra é um palíndromo (ou seja, se ela é lida da mesma forma de trás para frente, como "radar", "osso", "arara").

Especificamente, o programa fará o seguinte:

Ele analisa a palavra "radar".
Como "radar" é um palíndromo, a função define a variável r1 como 1 (que representa verdadeiro).
O programa imprime o número 1 na tela.

Passo a passo de como o código funciona:
A função questao3:

Recebe uma string (str) e um ponteiro para um número inteiro (resultado).
int n = strlen(str);: Calcula o tamanho da palavra.
*resultado = 1;: Assume inicialmente que a palavra é um palíndromo (verdadeiro).
O laço for: Ele percorre até a metade da palavra (n / 2). Em cada passo, ele compara a letra do começo (str[i]) com a letra correspondente no final (str[n - 1 - i]).
Se em algum momento as letras forem diferentes (ex: a primeira for diferente da última), ele define o resultado como 0 (falso) e o break interrompe a verificação.

Na função main:

É criada a variável palavra1[6] contendo a palavra "radar".
É passada a palavra e o endereço da variável r1 para a função questao3.
Como "radar" é de fato um palíndromo, a função termina com *resultado = 1.
O printf então imprime 1 no terminal.

Se você mudasse a palavra para "carro", por exemplo, o programa imprimiria 0.
```

---

## Questão 4

```c
#include <stdio.h>

void questao4(char str[10]) {
    int leitura = 1, escrita = 1;
    while (str[leitura] != '\0') {
        if (str[leitura] != str[leitura - 1]) {
            str[escrita] = str[leitura];
            escrita++;
        }
        leitura++;
    }
    str[escrita] = '\0';
}

int main() {
    char texto[10] = "12345568";
    questao4(texto);
    printf("Resultado: %s\n", texto);
    return 0;
}
```

**O que será impresso?**

```
Esse programa em linguagem C remove caracteres duplicados e consecutivos de uma string (ou seja, quando há uma letra/número duplicado logo ao lado do original, ele remove-a mantendo apenas uma unidade daquela sequência).

Especificamente, o programa fará o seguinte:

Ele analisa o texto "12345568".
Como o número '5' aparece repetido ao lado do outro '5', a função descarta a repetição em memória reestruturando ele em "1234568".
O programa imprime o texto impresso "Resultado: 1234568".

Passo a passo de como o código funciona:
A função questao4:

Recebe uma string (str).
int leitura = 1, escrita = 1;: Como o primeiro caractere da posição inicial 0 não tem como ser verificador de si na volta retroativa, eles começam varrendo na casa de índice de array 1 já na segunda posição para bater com a -1 e ir checando.
O laço while: Ele percorre a string a partir de leitura = 1 até achar a finalização com caractere nulo do loop no ('\0').
A verificação na linha if: Encontra qual o dígito e compara ele com a retaguarda em str[leitura - 1]. Se for distinto ou ele for único recopia para ser impresso copiando na string interna do local str[escrita] e incrementa o ponteiro numérico interno de escrita++. O ponteiro da via de escaneio avança normal.
str[escrita] = '\0';: Determina e dita o traço onde é o novo fim definitivo em '\0'.

Na função main:

É criada a variável texto[10] contendo os números "12345568".
É passada a palavra para a função questao4 e formatada internamente mudando seu tamanho sem avisar.
"12345568" condensa um "5" restando "1234568".
O printf da main() então imprime "Resultado: 1234568" final no console na tela.

Se você mudasse a leitura do texto para "aabbcc", por exemplo, o programa imprimiria "Resultado: abc", com limpeza dos colados.
```

---

## Questão 5

```c
#include <stdio.h>
#include <string.h>

int questao5(char palavra[]) {
    int n = strlen(palavra);
    for (int i = 0; i < n / 2; i++) {
        if (palavra[i] != palavra[n - 1 - i])
            printf("%c ",palavra[n - 1 - i]);
            return 0;
    }
    return 1;
}

int main() {
    char testes[10] = "12358474";
    int resultado = questao5(testes);
    return 0;
}
```

**O que será impresso?**

```
Esse programa em linguagem C compara o primeiro caractere de uma string com o último. Se forem iguais, imprime o último caractere e encerra a função retornando 0. Se os caracteres forem diferentes, encerra a função retornando 0. O return 1 nunca será executado.
 
```

---

*Boa avaliação! 🚀*
