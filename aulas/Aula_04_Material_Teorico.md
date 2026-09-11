# Aula 4 — Expressões Lógicas e Relacionais / Estruturas de Sequência

**Disciplina:** IAL-003 – Algoritmos e Programação de Computadores
**Curso:** Informática para Negócios — Fatec Mauá
**Professor:** Anderson Silva Vanin
**Data:** 04/09/2026 (Sexta-feira, 7h40–11h10) — Regular
**Ambiente:** Google Colab | **Linguagem:** Python 3

---

## Sumário

1. [Recapitulando a Aula 3](#1-recapitulando-a-aula-3)
2. [Expressões relacionais](#2-expressões-relacionais)
3. [Expressões lógicas](#3-expressões-lógicas)
4. [Estruturas básicas de sequência](#4-estruturas-básicas-de-sequência)
5. [Exercícios práticos](#5-exercícios-práticos)
6. [Resumo da aula](#resumo-da-aula)

---

## 1. Recapitulando a Aula 3

Na aula passada vimos que:

- Python tem sete operadores aritméticos: `+`, `-`, `*`, `/`, `//`, `%`, `**`;
- A **precedência** determina a ordem em que as operações são resolvidas (parênteses → potência →
  multiplicação/divisão → soma/subtração);
- Já conseguimos combinar `input()` com operadores aritméticos para montar pequenas calculadoras.

Hoje vamos aprender a **comparar valores** (expressões relacionais) e a **combinar comparações**
(expressões lógicas) — a base de tudo que envolve tomada de decisão em um programa. Também vamos
consolidar o conceito de **estrutura de sequência**, unindo tudo o que já aprendemos em programas
completos.

```python
# Relembrando a aula anterior
preco = float(input("Digite o preço do produto: R$ "))
quantidade = int(input("Digite a quantidade: "))
total = preco * quantidade
print("Total da compra: R$", total)
```

---

## 2. Expressões relacionais

**Expressões relacionais** (ou de comparação) comparam dois valores e o resultado é sempre um valor
do tipo `bool`: `True` (verdadeiro) ou `False` (falso).

| Operador | Significado | Exemplo | Resultado |
|---|---|---|---|
| `==` | Igual a | `5 == 5` | `True` |
| `!=` | Diferente de | `5 != 3` | `True` |
| `>` | Maior que | `5 > 3` | `True` |
| `<` | Menor que | `5 < 3` | `False` |
| `>=` | Maior ou igual a | `5 >= 5` | `True` |
| `<=` | Menor ou igual a | `5 <= 3` | `False` |

> ⚠️ **Atenção:** `==` (comparação) é diferente de `=` (atribuição)! Um erro muito comum de quem está
> começando é usar `=` quando o objetivo é comparar dois valores.

```python
a = 10
b = 7

print(a == b)   # False
print(a != b)   # True
print(a > b)    # True
print(a < b)    # False
print(a >= 10)  # True
print(b <= 5)   # False
```

Expressões relacionais também funcionam com texto (comparação alfabética/ordem lexicográfica) e são
muito usadas em conjunto com `input()`:

```python
idade = int(input("Digite sua idade: "))
maior_de_idade = idade >= 18
print("É maior de idade?", maior_de_idade)
```

---

## 3. Expressões lógicas

**Expressões lógicas** combinam duas ou mais expressões relacionais (ou valores booleanos) usando os
operadores `and`, `or` e `not`, também retornando sempre um `bool`.

| Operador | Significado | Regra |
|---|---|---|
| `and` | **E** — verdadeiro somente se **ambas** as condições forem verdadeiras | `True and True` → `True` |
| `or` | **OU** — verdadeiro se **pelo menos uma** das condições for verdadeira | `True or False` → `True` |
| `not` | **NÃO** — inverte o valor lógico | `not True` → `False` |
| `xor` | **OU_EXCLUSIVO** - A função avalia dois operandos e retorna True(ou 1) somente se as entradas forem diferentes. Se as entradas forem iguais, ela retorna False(ou 0) | `True ^ False` → `True` |

### Tabela-verdade do `and`

| A | B | A and B |
|---|---|---|
| `True` | `True` | `True` |
| `True` | `False` | `False` |
| `False` | `True` | `False` |
| `False` | `False` | `False` |

### Tabela-verdade do `or`

| A | B | A or B |
|---|---|---|
| `True` | `True` | `True` |
| `True` | `False` | `True` |
| `False` | `True` | `True` |
| `False` | `False` | `False` |

### Tabela-verdade do `xor`

| A | B | A or B |
|---|---|---|
| `True` | `True` | `False` |
| `True` | `False` | `True` |
| `False` | `True` | `True` |
| `False` | `False` | `False` |

### Tabela-verdade do `not`

| A | not A |
|---|---|
| `True` | `False` |
| `False` | `True` |

```python
idade = 20
tem_carteira = True

pode_dirigir = idade >= 18 and tem_carteira
print("Pode dirigir?", pode_dirigir)
```

```python
saldo = 50
tem_desconto = False

pode_comprar = saldo >= 100 or tem_desconto
print("Pode comprar?", pode_comprar)
```

```python
chove = True
print("Vou levar guarda-chuva?", chove)
print("Vou sem guarda-chuva?", not chove)
```

### Combinando várias condições

É possível combinar mais de duas condições na mesma expressão. Assim como nos operadores aritméticos,
existe uma ordem de avaliação: `not` é avaliado primeiro, depois `and`, e por último `or`. Na dúvida,
**use parênteses** para deixar a expressão mais clara:

```python
idade = 22
tem_ingresso = True
esta_na_lista = False

entrada_liberada = (idade >= 18) and (tem_ingresso or esta_na_lista)
print("Entrada liberada?", entrada_liberada)
```

---

## 4. Estruturas básicas de sequência

A **estrutura de sequência** é a mais simples de todas as estruturas de controle: as instruções são
executadas **uma após a outra, na ordem em que aparecem no código**, sem desvios e sem repetições.
Todo programa que escrevemos até agora seguiu uma estrutura sequencial.

### Características de um algoritmo sequencial

- Tem um **início** (entrada de dados ou definição de valores);
- Um **processamento** (cálculos, transformações);
- Um **fim** (saída/apresentação do resultado);
- Cada passo é executado **uma única vez**, na ordem escrita.

### Exemplo: calculando o IMC (Índice de Massa Corporal)

Este é um algoritmo tipicamente sequencial: recebe dois dados, faz um cálculo com eles e mostra o
resultado — sem nenhum desvio de fluxo.

```python
peso = float(input("Digite seu peso (kg): "))
altura = float(input("Digite sua altura (m): "))

imc = peso / (altura ** 2)

print("Seu IMC é:", imc)
```

> Note que, por enquanto, **não estamos decidindo nada** (não dizemos se o IMC está "normal" ou
> "alto") — apenas calculamos e mostramos o valor. Structures de **seleção** (que permitem tomar
> decisões com `if`) serão vistas em breve.

### Exemplo: cadastro simples com verificação lógica

Podemos usar expressões relacionais e lógicas dentro de um algoritmo sequencial, sem ainda "desviar"
o fluxo — apenas calculando e exibindo o resultado da comparação:

```python
nome = input("Digite seu nome: ")
idade = int(input("Digite sua idade: "))
matriculado = True

pode_acessar_conteudo = (idade >= 18) and matriculado

print("Nome:", nome)
print("Idade:", idade)
print("Pode acessar o conteúdo?", pode_acessar_conteudo)
```

### Exemplo: calculando a média ponderada

```python
nota1 = float(input("Digite a nota da P1: "))
nota2 = float(input("Digite a nota da P2: "))
nota3 = float(input("Digite a nota da P3: "))

media = (nota1 * 2 + nota2 * 3 + nota3 * 5) / 10
aprovado = media >= 6.0

print("Média final:", media)
print("Aprovado?", aprovado)
```

---

## 5. Exercícios práticos

Resolva os exercícios abaixo em um novo notebook do Google Colab (ou nas células indicadas pelo
professor).

### Exercício 1
Peça dois números ao usuário e exiba o resultado das seis comparações possíveis entre eles: `==`,
`!=`, `>`, `<`, `>=`, `<=`.

### Exercício 2
Peça ao usuário a idade e se ele possui carteira de motorista (`True`/`False`, convertendo o texto
digitado). Exiba se a pessoa **pode dirigir** (precisa ter 18 anos ou mais **e** possuir carteira).

### Exercício 3
Peça ao usuário duas notas (P1 e P2) e calcule a média simples entre elas. Em seguida, exiba se o
aluno está **aprovado** (`True`) considerando que a média mínima de aprovação é `6.0`.

### Exercício 4
Construa, de forma sequencial, um pequeno programa de "checkout" de loja: peça o valor da compra e se
o cliente possui cupom de desconto (`True`/`False`). Exiba se a compra **dá direito a frete grátis**
(valor da compra maior ou igual a R$ 150 **ou** possui cupom de desconto).

### Exercício 5 (desafio)
Peça ao usuário três números inteiros e, usando apenas expressões relacionais e lógicas (ainda sem
`if`), exiba se **os três números são iguais entre si** (`True` ou `False`).

> 💡 **Entrega:** salve seu notebook no Google Drive (*Arquivo → Salvar uma cópia no Drive*) com o
> nome `Aula04_SeuNome.ipynb` e envie o link conforme orientação do professor.

---

## Resumo da aula

- **Expressões relacionais** (`==`, `!=`, `>`, `<`, `>=`, `<=`) comparam valores e retornam `bool`.
- **Expressões lógicas** (`and`, `or`, `not`) combinam condições, seguindo as tabelas-verdade de cada
  operador.
- A **estrutura de sequência** é a execução de instruções, uma após a outra, sem desvios de fluxo —
  toda a base dos programas que já escrevemos até aqui.
- Já é possível calcular e **avaliar condições** dentro de um algoritmo sequencial, mesmo sem ainda
  "decidir" o que fazer com o resultado — isso será o próximo passo.

## Para a próxima aula

Vamos estudar **representações gráficas de algoritmos**: fluxogramas e pseudocódigo, e como eles se
relacionam com o código Python que já estamos escrevendo.
