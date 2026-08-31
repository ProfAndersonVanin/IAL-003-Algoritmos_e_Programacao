# Aula 2 — Tipos de Dados Básicos e Entrada de Dados

**Disciplina:** IAL-003 – Algoritmos e Programação de Computadores
**Curso:** Informática para Negócios — Fatec Mauá
**Professor:** Anderson Silva Vanin
**Data:** 01/09/2026 (Terça-feira, 7h40–9h20) — Reposição (repõe 07/08)
**Ambiente:** Google Colab | **Linguagem:** Python 3

---

## Sumário

1. [Recapitulando a Aula 1](#1-recapitulando-a-aula-1)
2. [Tipos de dados básicos em Python](#2-tipos-de-dados-básicos-em-python)
3. [Conversão entre tipos](#3-conversão-entre-tipos-type-casting)
4. [Entrada de dados com `input()`](#4-entrada-de-dados-com-input)
5. [Exercícios práticos](#5-exercícios-práticos)
6. [Resumo da aula](#resumo-da-aula)

---

## 1. Recapitulando a Aula 1

Na aula passada vimos que:

- **Algoritmo** é uma sequência finita e ordenada de passos para resolver um problema;
- O **Google Colab** organiza o trabalho em células de texto (Markdown) e de código;
- `print()` exibe informações na tela;
- **Variáveis** guardam valores na memória e podem ser reatribuídas.

Hoje vamos aprofundar: **que tipos de valores** uma variável pode guardar, e como fazer nosso
programa **receber informações digitadas pelo usuário**, em vez de sempre usar valores fixos no
código.

```python
# Relembrando a aula anterior
nome = "Ana"
idade = 20
print("Nome:", nome, "| Idade:", idade)
```

---

## 2. Tipos de dados básicos em Python

Toda variável, além de um valor, tem um **tipo de dado**, que determina que tipo de informação ela
guarda e quais operações podem ser feitas com ela. Os quatro tipos básicos que usaremos neste curso
são:

| Tipo | Nome em Python | Representa | Exemplo |
|---|---|---|---|
| Inteiro | `int` | Números inteiros (sem casas decimais) | `10`, `-3`, `0` |
| Ponto flutuante | `float` | Números com casas decimais | `3.14`, `-0.5`, `10.0` |
| Texto (string) | `str` | Cadeias de caracteres, sempre entre aspas | `"Ana"`, `'Fatec'` |
| Booleano | `bool` | Valor lógico: verdadeiro ou falso | `True`, `False` |

Podemos descobrir o tipo de qualquer valor ou variável usando a função `type()`:

```python
idade = 20
altura = 1.75
nome = "Ana"
aprovado = True

print(idade, "->", type(idade))
print(altura, "->", type(altura))
print(nome, "->", type(nome))
print(aprovado, "->", type(aprovado))
```

### Um detalhe importante sobre `str`

Texto sempre fica entre aspas simples `'...'` ou duplas `"..."` — mesmo que o conteúdo seja um número!
Isso muda completamente como o Python trata o valor:

```python
numero_inteiro = 10
numero_como_texto = "10"

print(type(numero_inteiro))
print(type(numero_como_texto))

# Isso funciona (soma matemática):
print(numero_inteiro + 5)

# Isso NÃO funcionaria da mesma forma - "10" é texto, não número.
# print(numero_como_texto + 5)   # geraria erro
```

### Operadores lógicos com booleanos

O tipo `bool` só tem dois valores possíveis: `True` (verdadeiro) e `False` (falso). Ele normalmente
aparece como resultado de uma **comparação** — assunto que aprofundaremos na aula sobre expressões
lógicas. Por hoje, basta saber que ele existe:

```python
maior_de_idade = 18 >= 18
print(maior_de_idade)
print(type(maior_de_idade))
```

---

## 3. Conversão entre tipos (*type casting*)

Muitas vezes precisamos converter um valor de um tipo para outro — por exemplo, transformar um texto
`"25"` no número `25` para poder fazer contas. Usamos funções de conversão:

| Função | Converte para |
|---|---|
| `int(valor)` | Inteiro |
| `float(valor)` | Ponto flutuante |
| `str(valor)` | Texto |
| `bool(valor)` | Booleano |

```python
texto_numero = "25"
numero = int(texto_numero)

print(texto_numero, "->", type(texto_numero))
print(numero, "->", type(numero))

print(numero + 5)   # agora funciona, pois numero é int
```

```python
# Outros exemplos de conversão
preco_texto = "19.90"
preco = float(preco_texto)
print(preco, type(preco))

idade_numero = 20
idade_texto = str(idade_numero)
print(idade_texto, type(idade_texto))
```

---

## 4. Entrada de dados com `input()`

Até agora, todos os valores das nossas variáveis estavam **fixos no código**. Na prática, a maioria
dos programas precisa **receber dados de quem está usando** — um nome, uma idade, um valor de compra
etc. Para isso usamos a função `input()`.

```python
variavel = input("Mensagem para o usuário: ")
```

O texto entre parênteses é a **mensagem exibida** ao usuário (opcional, mas recomendada). O programa
**pausa a execução** até que a pessoa digite algo e pressione Enter.

> ⚠️ **Muito importante:** o `input()` **sempre retorna um valor do tipo `str` (texto)**, mesmo que a
> pessoa digite um número. Se você precisar fazer conta com o valor digitado, terá que **converter**
> com `int()` ou `float()`.

```python
nome = input("Qual é o seu nome? ")
print("Olá,", nome, "! Seja bem-vindo(a) à disciplina.")
```

```python
idade_texto = input("Qual é a sua idade? ")
print(type(idade_texto))   # str, mesmo digitando um número

idade = int(idade_texto)   # convertendo para int
print(type(idade))
print("Ano que vem você terá", idade + 1, "anos.")
```

Também é possível converter na mesma linha em que capturamos o valor, deixando o código mais curto:

```python
altura = float(input("Qual é a sua altura em metros (ex: 1.70)? "))
print("Sua altura é", altura, "m.")
print(type(altura))
```

---

## 5. Exercícios práticos

Resolva os exercícios abaixo em um novo notebook do Google Colab (ou nas células indicadas pelo
professor).

### Exercício 1
Peça ao usuário o nome e o curso (dois `input()` diferentes) e exiba uma mensagem de boas-vindas
personalizada, no formato:

```
Olá, <nome>! Você está matriculado(a) em <curso>.
```

### Exercício 2
Peça ao usuário sua idade (com `input()`), converta para `int` e exiba o **tipo** da variável antes
e depois da conversão, além do valor da idade daqui a 10 anos.

### Exercício 3
Peça ao usuário o preço de um produto (`float`) e a quantidade comprada (`int`). Exiba o tipo de cada
variável capturada. (Não é necessário calcular o total ainda — faremos isso na próxima aula, com
operadores aritméticos.)

### Exercício 4 (desafio)
Crie um pequeno "cadastro" que peça ao usuário: nome, idade e se é aluno bolsista (digite `True` ou
`False`). Converta cada valor para o tipo adequado (`str`, `int`, `bool`) e exiba o tipo de cada
variável usando `type()`.

> Dica: para converter texto `"True"`/`"False"` digitado em `bool` de verdade, você pode comparar o
> texto digitado com a string `"True"`, assim: `valor == "True"`.

> 💡 **Entrega:** salve seu notebook no Google Drive (*Arquivo → Salvar uma cópia no Drive*) com o
> nome `Aula02_SeuNome.ipynb` e envie o link conforme orientação do professor.

---

## Resumo da aula

- Os quatro tipos de dados básicos em Python são `int`, `float`, `str` e `bool`.
- `type()` mostra o tipo de um valor ou variável.
- É possível converter entre tipos com `int()`, `float()`, `str()` e `bool()`.
- `input()` captura dados digitados pelo usuário, **sempre como `str`** — converta quando precisar
  fazer contas.

## Para a próxima aula

Vamos estudar **expressões aritméticas e operadores** (`+`, `-`, `*`, `/`, `//`, `%`, `**`) e a
**precedência** entre eles — a base para fazer cálculos em Python.
