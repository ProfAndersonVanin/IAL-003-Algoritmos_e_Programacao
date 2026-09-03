# Aula 3 — Expressões Aritméticas e Operadores

**Disciplina:** IAL-003 – Algoritmos e Programação de Computadores
**Curso:** Informática para Negócios — Fatec Mauá
**Professor:** Anderson Silva Vanin
**Data:** 02/09/2026 (Quarta-feira, 7h40–9h20) — Reposição (repõe 14/08)
**Ambiente:** Google Colab | **Linguagem:** Python 3

---

## Sumário

1. [Recapitulando a Aula 2](#1-recapitulando-a-aula-2)
2. [Operadores aritméticos](#2-operadores-aritméticos)
3. [Precedência de operadores](#3-precedência-de-operadores)
4. [Combinando aritmética com `input()`](#4-combinando-aritmética-com-input)
5. [Exercícios práticos](#5-exercícios-práticos)
6. [Resumo da aula](#resumo-da-aula)

---

## 1. Recapitulando a Aula 2

Na aula passada vimos que:

- Python tem quatro tipos de dados básicos: `int`, `float`, `str` e `bool`;
- É possível converter entre tipos com `int()`, `float()`, `str()` e `bool()`;
- `input()` captura dados digitados pelo usuário, sempre como `str`.

Hoje vamos aprender a **fazer contas** em Python: os operadores aritméticos e a ordem em que eles são
resolvidos (precedência) — a base de qualquer cálculo em um programa.

```python
# Relembrando a aula anterior
idade_texto = input("Digite sua idade: ")
idade = int(idade_texto)
print("Você digitou:", idade, "-", type(idade))
```

---

## 2. Operadores aritméticos

Python oferece sete operadores aritméticos básicos:

| Operador | Nome | O que faz | Exemplo | Resultado |
|---|---|---|---|---|
| `+` | Adição | Soma dois valores | `5 + 2` | `7` |
| `-` | Subtração | Subtrai o segundo valor do primeiro | `5 - 2` | `3` |
| `*` | Multiplicação | Multiplica dois valores | `5 * 2` | `10` |
| `/` | Divisão | Divide e **sempre** retorna `float` | `5 / 2` | `2.5` |
| `//` | Divisão inteira (floor division) | Divide e descarta a parte decimal | `5 // 2` | `2` |
| `%` | Módulo (resto da divisão) | Retorna o **resto** da divisão inteira | `5 % 2` | `1` |
| `**` | Potenciação | Eleva o primeiro valor à potência do segundo | `5 ** 2` | `25` |

Vamos ver cada um funcionando na prática:

```python
a = 5
b = 2

print("Soma:", a + b)
print("Subtração:", a - b)
print("Multiplicação:", a * b)
print("Divisão:", a / b)
print("Divisão inteira:", a // b)
print("Módulo (resto):", a % b)
print("Potenciação:", a ** b)
```

### Por que `/` e `//` são diferentes?

- `/` (divisão comum) **sempre** devolve um `float`, mesmo quando o resultado é "redondo";
- `//` (divisão inteira) devolve a parte inteira da divisão, **descartando** o restante — muito usada,
  por exemplo, para calcular quantas caixas fechadas cabem em uma quantidade de itens.

### Para que serve o operador `%` (módulo)?

O módulo devolve o que **sobra** de uma divisão. É extremamente útil para, por exemplo, verificar se
um número é par ou ímpar (resto da divisão por 2), ou calcular horas/minutos a partir de um total de
minutos.

```python
numero = 17

print(numero / 2)    # divisão comum -> 8.5
print(numero // 2)   # divisão inteira -> 8
print(numero % 2)    # resto -> 1 (então o número é ímpar)
```

---

## 3. Precedência de operadores

Assim como na matemática tradicional, o Python segue uma **ordem de prioridade** para resolver
expressões com mais de um operador. Da maior para a menor prioridade:

1. `()` — parênteses (sempre resolvidos primeiro);
2. `**` — potenciação;
3. `*`, `/`, `//`, `%` — multiplicação, divisão, divisão inteira e módulo (mesma prioridade entre si);
4. `+`, `-` — adição e subtração (mesma prioridade entre si).

Quando operadores têm a **mesma prioridade**, o Python resolve **da esquerda para a direita**.

> 💡 **Dica prática:** na dúvida, **use parênteses**. Eles deixam a expressão mais clara para quem lê
> o código e evitam erros de interpretação.

```python
# Sem parênteses - segue a ordem de precedência
resultado1 = 2 + 3 * 4
print("2 + 3 * 4 =", resultado1)   # multiplicação primeiro: 2 + 12 = 14

# Com parênteses - a soma é forçada a acontecer primeiro
resultado2 = (2 + 3) * 4
print("(2 + 3) * 4 =", resultado2)  # 5 * 4 = 20
```

```python
# Expressão mais completa
expressao = 10 + 2 ** 3 - 4 / 2
print(expressao)

# Resolução passo a passo:
# 1) potência:      2 ** 3 = 8      -> 10 + 8 - 4 / 2
# 2) divisão:        4 / 2 = 2.0    -> 10 + 8 - 2.0
# 3) soma/subtração (esquerda p/ direita): 10 + 8 = 18, 18 - 2.0 = 16.0
```

---

## 4. Combinando aritmética com `input()`

Agora que sabemos capturar dados do usuário (Aula 2) e fazer contas (Aula 3), podemos escrever
programas realmente úteis:

```python
preco = float(input("Digite o preço do produto: R$ "))
quantidade = int(input("Digite a quantidade: "))

total = preco * quantidade
print("Total da compra: R$", total)
```

```python
nota1 = float(input("Digite a primeira nota: "))
nota2 = float(input("Digite a segunda nota: "))

media = (nota1 + nota2) / 2
print("Sua média é:", media)
```

---

## 5. Exercícios práticos

Resolva os exercícios abaixo em um novo notebook do Google Colab (ou nas células indicadas pelo
professor).

### Exercício 1
Peça dois números ao usuário (com `input()`, convertendo para `float`) e exiba o resultado das
quatro operações básicas entre eles: soma, subtração, multiplicação e divisão.

### Exercício 2
Peça ao usuário um número inteiro e exiba o resultado do resto da divisão por 2 (`%`), indicando se
o número é **par** ou **ímpar**. (Por enquanto, apenas exiba o valor do resto — a estrutura `if` para
decidir "par ou ímpar" automaticamente veremos em breve, na aula de estruturas de seleção.)

### Exercício 3
Peça ao usuário a quantidade total de minutos de uma ligação e calcule quantas **horas** e quantos
**minutos restantes** isso representa, usando `//` e `%`.

Exemplo: 130 minutos = 2 horas e 10 minutos.

### Exercício 4 (desafio)
Escreva um programa que calcule a área de um círculo (`π * raio ** 2`), pedindo o raio ao usuário. Use
`3.14159` no lugar de π. Exiba o resultado com a mensagem:

```
A área do círculo é: <valor>
```

> 💡 **Entrega:** salve seu notebook no Google Drive (*Arquivo → Salvar uma cópia no Drive*) com o
> nome `Aula03_SeuNome.ipynb` e envie o link conforme orientação do professor.

---

## Resumo da aula

- Python tem sete operadores aritméticos: `+`, `-`, `*`, `/`, `//`, `%`, `**`.
- `/` sempre resulta em `float`; `//` descarta a parte decimal; `%` devolve o resto da divisão.
- A **precedência** segue: parênteses → potência → multiplicação/divisão/`//`/`%` → soma/subtração,
  resolvendo da esquerda para a direita quando a prioridade é igual.
- Combinar `input()` com operadores aritméticos permite construir pequenas calculadoras.

## Para a próxima aula

Vamos estudar **expressões lógicas e relacionais** (`and`, `or`, `not`, `==`, `!=`, `>`, `<`) e as
**estruturas básicas de sequência** — os primeiros passos rumo às estruturas de decisão.
