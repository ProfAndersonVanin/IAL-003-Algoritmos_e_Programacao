# Aula 1 — Introdução à Lógica de Programação e Primeiro Programa em Python

**Disciplina:** IAL-003 – Algoritmos e Programação de Computadores
**Curso:** Informática para Negócios — Fatec Mauá
**Professor:** Anderson Silva Vanin
**Data:** 28/08/2026 (Sexta-feira, 7h40–11h10)
**Ambiente:** Google Colab | **Linguagem:** Python 3

---

## Sumário

1. [Apresentação da disciplina](#1-apresentação-da-disciplina)
2. [Introdução à Lógica de Programação](#2-introdução-à-lógica-de-programação)
3. [Ambiente Google Colab](#3-ambiente-google-colab)
4. [Primeiro programa em Python: `print()` e variáveis](#4-primeiro-programa-em-python-print-e-variáveis)
5. [Exercícios práticos](#5-exercícios-práticos)
6. [Resumo da aula](#resumo-da-aula)

---

## 1. Apresentação da disciplina

### Ementa

A disciplina **IAL-003 – Algoritmos e Programação de Computadores** tem como objetivo desenvolver a
capacidade de **analisar problemas** e **projetar soluções computacionais** para eles, por meio de
metodologias, técnicas e ferramentas de programação. Ao longo do semestre vamos estudar:

- Método para desenvolvimento de algoritmos;
- Modularidade e abstração;
- Tipos de dados básicos e representações gráficas dos principais comandos de uma linguagem
  procedural;
- Expressões aritméticas, lógicas e literais;
- Estruturas básicas de programas: **sequência**, **iteração**, **seleção simples e múltipla**;
- Desenvolvimento de programas estruturados que manipulam essas estruturas básicas.

Toda a parte prática será feita em **Python**, utilizando o **Google Colab** como ambiente de
desenvolvimento — não é necessário instalar nada no computador, basta um navegador e uma conta Google.

### Critérios de avaliação

| Avaliação | Conteúdo cobrado | Data prevista |
|---|---|---|
| P1 | Lógica de algoritmos, tipos de dados, expressões, sequência e seleção | 16/10/2026 |
| P2 | Repetição, listas, matrizes, strings e funções | 13/11/2026 |
| P3 | Entrega/apresentação de projeto final estruturado | 04/12/2026 |

Além das provas, listas de exercícios e um **projeto prático integrador** também compõem a avaliação
contínua ao longo do semestre.

### Combinados de sala

- Notebooks e exercícios ficam salvos no seu Google Drive — organize uma pasta por aula.
- Traga dúvidas sempre para o início da aula seguinte: lógica de programação é cumulativa.
- Não existe "aula perdida" — reposições estão previstas no cronograma oficial da disciplina.

---

## 2. Introdução à Lógica de Programação

### O que é um algoritmo?

Um **algoritmo** é uma sequência finita e ordenada de passos (instruções) que, executados nessa
ordem, resolvem um problema ou realizam uma tarefa. Não é exclusivo da computação: uma receita de
bolo, um manual de montagem de móvel e o trajeto que você faz de casa até a faculdade são todos
algoritmos.

**Características de um bom algoritmo:**

- **Finitude** — precisa terminar em algum momento (número finito de passos);
- **Precisão** — cada passo deve ser claro e sem ambiguidade;
- **Definição de entradas e saídas** — o que ele recebe e o que ele produz;
- **Eficácia** — cada instrução deve ser executável.

### Exemplo do dia a dia: "Trocar uma lâmpada"

1. Desligar o interruptor;
2. Pegar uma escada;
3. Subir na escada;
4. Retirar a lâmpada queimada;
5. Colocar a lâmpada nova;
6. Descer da escada;
7. Ligar o interruptor.

Note que a **ordem importa**: se invertermos os passos 1 e 4, por exemplo, corremos risco de choque
elétrico. Programar é, essencialmente, **descrever passos como esses de forma que o computador
consiga entender e executar**.

### Do algoritmo ao programa

| Conceito | O que é |
|---|---|
| **Algoritmo** | A ideia, a sequência lógica de passos (independe de linguagem) |
| **Pseudocódigo** | Uma escrita do algoritmo próxima da linguagem humana, mas estruturada |
| **Fluxograma** | Representação gráfica do algoritmo, usando símbolos padronizados |
| **Programa** | O algoritmo escrito em uma linguagem de programação (neste curso, **Python**) que o computador executa |

> Fluxogramas e pseudocódigo serão estudados com mais detalhe em uma próxima aula. Por hoje, o
> importante é entender que **pensar em algoritmo é pensar em passos ordenados, antes de qualquer
> código**.

### Por que Python?

Python é uma linguagem de **alto nível**, com sintaxe próxima da linguagem natural, muito usada em
Ciência de Dados, automação, desenvolvimento web e ensino de lógica de programação — por isso é uma
ótima porta de entrada para quem está começando.

---

## 3. Ambiente Google Colab

O **Google Colaboratory (Colab)** é um ambiente gratuito, baseado em nuvem, para escrever e executar
código Python — os arquivos usados nele são **notebooks** (extensão `.ipynb`).

### Estrutura de um notebook

Um notebook é dividido em **células**. Existem dois tipos principais:

- **Células de texto (Markdown)** — usadas para explicações, títulos, listas, tabelas etc.;
- **Células de código** — onde escrevemos e executamos comandos Python.

### Como executar uma célula

- **Shift + Enter** — executa e vai para a próxima célula;
- **Ctrl + Enter** — executa e permanece na mesma célula;
- Clique no ícone de "play" ▶️ no canto esquerdo da célula.

### Atalhos úteis

| Atalho | Ação |
|---|---|
| `Shift + Enter` | Executar célula atual e ir para a próxima |
| `Ctrl + Enter` | Executar célula atual (permanece nela) |
| `Ctrl + M B` | Inserir célula abaixo |
| `Ctrl + M A` | Inserir célula acima |
| `Ctrl + M D` (2x) | Excluir célula |
| `Ctrl + M M` | Transformar célula em Markdown |
| `Ctrl + M Y` | Transformar célula em código |

**Exemplo — primeira execução:**

```python
# Pressione Shift + Enter para executar esta célula.
print("Ambiente Colab funcionando! ✅")
```

> **Dica:** o número que aparece à esquerda da célula (`[1]`, `[2]`, ...) indica a **ordem de
> execução**. No Colab é possível executar as células fora de ordem — sempre fique atento à ordem de
> execução ao depurar um problema.

---

## 4. Primeiro programa em Python: `print()` e variáveis

### A função `print()`

`print()` é uma **função** pronta da linguagem Python usada para exibir informações na tela (saída
padrão). É, normalmente, o primeiro comando que qualquer pessoa aprende em uma nova linguagem — o
clássico "Hello, World!".

```python
print("Hello, World!")
```

Podemos imprimir texto (entre aspas — chamado de **string**), números, ou vários valores separados
por vírgula:

```python
print("Bem-vindo à disciplina de Algoritmos!")
print(2026)
print("Turma:", "Informática para Negócios", "- 2º Ciclo")
```

### Variáveis

Uma **variável** é um espaço de memória, identificado por um nome, que guarda um valor que pode ser
usado (e alterado) ao longo do programa. Pense nela como uma "caixa com etiqueta".

Em Python, criamos uma variável simplesmente **atribuindo** um valor a um nome, usando o sinal `=`:

```python
variavel = valor
```

Não é necessário declarar o tipo da variável antes — o Python identifica automaticamente
(**tipagem dinâmica**).

```python
nome = "Ana"
idade = 20
altura = 1.68

print(nome)
print(idade)
print(altura)
```

Podemos combinar texto e variáveis na mesma chamada de `print()`:

```python
nome = "Ana"
idade = 20

print("Nome:", nome)
print("Idade:", idade)
print("Nome:", nome, "| Idade:", idade)
```

### Regras para nomear variáveis em Python

- Pode conter letras, números e `_` (underline), mas **não pode começar com número**;
- **Não pode conter espaços** — use `nome_completo`, não `nome completo`;
- É **case-sensitive**: `idade`, `Idade` e `IDADE` são três variáveis diferentes;
- Evite acentos e caracteres especiais;
- Não pode ser uma palavra reservada da linguagem (`print`, `if`, `for`, `while`, etc.);
- Por convenção, usa-se `snake_case` (letras minúsculas separadas por `_`) para nomes de variáveis em
  Python.

### Reatribuição

O valor de uma variável pode ser alterado a qualquer momento — por isso o nome "variável":

```python
pontuacao = 0
print("Pontuação inicial:", pontuacao)

pontuacao = 10
print("Pontuação após 1ª rodada:", pontuacao)

pontuacao = pontuacao + 5   # usa o valor atual para calcular o novo valor
print("Pontuação após 2ª rodada:", pontuacao)
```

---

## 5. Exercícios práticos

Resolva os exercícios abaixo em um novo notebook do Google Colab (ou nas células de código indicadas
pelo professor). Use `Shift + Enter` para executar e conferir o resultado de cada um.

### Exercício 1
Escreva um programa que exiba seu nome completo na tela usando `print()`.

### Exercício 2
Crie três variáveis: `nome`, `curso` e `periodo`, com seus próprios dados, e depois exiba as três em
uma única chamada de `print()`, formatadas como no exemplo:

```
Nome: <seu nome> | Curso: <seu curso> | Período: <seu período>
```

### Exercício 3
Crie uma variável chamada `idade` com sua idade atual. Em seguida, some 1 a essa variável (simulando
"fazer aniversário") e exiba o valor **antes** e **depois** da soma.

### Exercício 4 (desafio)
Usando apenas variáveis e `print()`, monte um pequeno "cartão de apresentação" com pelo menos quatro
informações suas (nome, cidade, curso, um hobby, por exemplo), exibindo cada uma em uma linha
diferente.

> 💡 **Entrega:** salve seu notebook no Google Drive (*Arquivo → Salvar uma cópia no Drive*) com o
> nome `Aula01_SeuNome.ipynb` e envie o link conforme orientação do professor.

---

## Resumo da aula

- Um **algoritmo** é uma sequência finita e ordenada de passos para resolver um problema.
- O **Google Colab** organiza o trabalho em **células** de texto (Markdown) e de código, executadas
  com `Shift + Enter`.
- `print()` é a função usada para exibir informações na tela.
- **Variáveis** guardam valores na memória, com tipagem dinâmica e regras próprias de nomenclatura.

## Para a próxima aula

Vamos estudar **tipos de dados básicos em Python** (`int`, `float`, `str`, `bool`) e como capturar
dados digitados pelo usuário com a função `input()`.
