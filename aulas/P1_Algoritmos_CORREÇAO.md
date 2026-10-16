# AVALIAÇÃO OFICIAL – P1 (PROVA ESCRITA, INDIVIDUAL E SEM CONSULTA)

| | |
|---|---|
| **Curso** | Informática para Negócios |
| **Disciplina** | Algoritmos e Programação de Computadores – IAL 003 |
| **Professor(a)** | Anderson Silva Vanin |
| **Aluno(a)** (nome completo) | |
| **RA** | |
| **Ciclo (semestre)** | 2º |
| **Turno** | Matutino |
| **Data** | 16/10/2026 |
| **Nota** | |
| **Vistas de prova** | *(assine este campo após a correção)* |

---

**Instruções:**

- Prova individual e sem consulta;
- Leia atentamente cada enunciado antes de responder;
- Nas questões de código, escreva exatamente o que seria exibido na tela ao executar o programa;
- Valor total da prova: 10,0 pontos. A pontuação parcial de cada item está indicada entre parênteses.

---

### Questão 1 (0,5 pt)

Marque a alternativa que melhor define o que é um algoritmo:

a) ( ) Um programa escrito exclusivamente na linguagem Python para realizar uma tarefa ou problema.

**b) (X) Uma sequência finita e ordenada de passos que resolve um problema ou realiza uma tarefa.**

c) ( ) Um conjunto de regras que só pode ser executado por um computador uma única vez.

d) ( ) Um tipo de variável usado para armazenar números inteiros a fim de realizar cálculos complexos.

---

### Questão 2 (0,5 pt)

São características de um bom algoritmo, **exceto**:

a) ( ) Finitude — deve terminar em um número finito de passos.

b) ( ) Precisão — cada passo deve ser claro e sem ambiguidade.

**c) (X) Ambiguidade — mais de uma interpretação para o mesmo passo.**

d) ( ) Eficácia — cada instrução deve ser executável.

---

### Questão 3 (0,5 pt)

O programa abaixo deveria calcular o IMC (peso dividido pela altura ao quadrado), mas gera um erro ao ser executado:

```python
altura = float(input("Digite a altura (m): "))
peso = float(input("Digite o peso (kg): "))
imc = peso / (Altura ** 2)
print("IMC:", imc)
```

a) Em qual linha ocorre o erro e qual é a causa? *(0,25 pt)*

**Erro na linha 3: Altura (maiúscula) não existe, a variável criada é altura; Python diferencia maiúsculas de minúsculas (NameError)**

b) Reescreva a linha incorreta de forma que o programa funcione. *(0,25 pt)*

**imc = peso / (altura ** 2)**

---

### Questão 4 (0,5 pt)

Qual será a saída exibida na tela ao executar o código abaixo?

```python
print("Fatec", "Mauá", 2026)
```

Resposta:

**Fatec Mauá 2026**

---

### Questão 5 (0,5 pt)

Assinale a alternativa que contém um nome de variável válido em Python:

a) ( ) `2idade`

b) ( ) `nome completo`

**c) (X) `nota_final`**

d) ( ) `class`

---

### Questão 6 (0,5 pt)

Observe o código abaixo e informe o tipo de dado (`int`, `float`, `str` ou `bool`) de cada variável: *(0,125 pt por variável)*

```python
a = 10
b = 3.5
c = "Python"
d = True
```

| Variável | Tipo |
|---|---|
| `a` | **int** |
| `b` | **float** |
| `c` | **str** |
| `d` | **bool** |

---

### Questão 7 (0,75 pt)

Considere o trecho de código a seguir:

```python
idade = "20"
ano_que_vem = idade + 1
```

a) Esse código gera um erro ao ser executado? Justifique. *(0,5 pt)*

**Sim, gera erro (`TypeError`): `idade` é `str` e não é possível somar `str` com `int`.**

b) Reescreva a segunda linha para que o código funcione corretamente. *(0,25 pt)*

**ano_que_vem = int(idade) + 1**

---

### Questão 8 (0,5 pt)

Sobre a função `input()`, assinale a afirmação correta:

a) ( ) `input()` sempre retorna um valor do tipo `int`.

**b) (X) `input()` sempre retorna um valor do tipo `str`.**

c) ( ) `input()` identifica automaticamente se o valor digitado é texto ou número.

d) ( ) `input()` não pode ser usado junto com `print()`.

---

### Questão 9 (0,5 pt)

Calcule o resultado de cada expressão aritmética abaixo: *(0,125 pt por item)*

a) `10 + 3 * 2` = **16**

b) `10 / 3` = **3.33…**

c) `10 // 3` = **3**

d) `10 % 3` = **1**

---

### Questão 10 (0,75 pt)

Explique, com suas palavras, a diferença entre os operadores `/` e `//` em Python. Em seguida, dê um exemplo de uma situação prática em que faria sentido usar o operador `%`. *(diferença entre `/` e `//`: 0,5 pt; exemplo de uso do `%`: 0,25 pt)*

**`/` é a divisão comum e sempre retorna `float`; `//` é a divisão inteira e descarta a parte decimal.**

**qualquer situação coerente (par/ímpar, converter minutos em horas e minutos, sobra de uma divisão em grupos etc.)**

---

### Questão 11 (0,75 pt)

Qual é o resultado da expressão abaixo? Mostre o passo a passo da resolução, respeitando a ordem de precedência dos operadores. *(passo a passo: 0,5 pt; resultado final: 0,25 pt)*

```python
resultado = 2 + 4 ** 2 - 6 / 3
```

Resolução e resposta:

**`4 ** 2 = 16`; `6 / 3 = 2.0`; `2 + 16 = 18`; `18 - 2.0`. *(Potência primeiro e divisão antes da soma/subtração.)***

---

### Questão 12 (0,5 pt)

Para cada expressão relacional abaixo, indique se o resultado é `True` ou `False`: *(0,125 pt por item)*

a) `7 > 5` → **True**

b) `3 == 3.0` → **True**

c) `"ana" != "Ana"` → **True**

d) `10 <= 9` → **False**

---

### Questão 13 (0,75 pt)

Considere as variáveis:

```python
idade = 17
tem_autorizacao = True
```

Qual é o resultado da expressão abaixo? *(0,25 pt)*

```python
idade >= 18 and tem_autorizacao
```

Resposta:

**False**

Reescreva a expressão de forma que o resultado seja `True`, sem alterar o valor de `idade`. *(0,5 pt)*

**qualquer expressão que dê `True` sem mudar `idade`, por exemplo `idade >= 17 and tem_autorizacao` ou `idade < 18 and tem_autorizacao`.**

---

### Questão 14 (0,5 pt)

O que caracteriza uma estrutura de sequência em um algoritmo?

a) ( ) A repetição de um bloco de instruções várias vezes podendo conter desvios na programação.

**b) (X) A execução de instruções, uma após a outra, na ordem em que aparecem, sem desvios.**

c) ( ) A escolha entre dois ou mais caminhos possíveis, de acordo com uma condição.

d) ( ) A divisão do programa em funções menores que são executadas sequencialmente.

---

### Questão 15 (0,5 pt)

Considere as variáveis e a expressão abaixo:

```python
a = 8
b = 3
resultado = a % b == 2 or not (a > b)
```

Qual é o valor armazenado em `resultado`?

**a) (X) `True` (`8 % 3 = 2`, `2 == 2` é `True`; com `or`, o resultado é `True`**

b) ( ) `False`

c) ( ) `2`

d) ( ) A expressão gera um erro de execução.

---

### Questão 16 (1,5 pt)

Escreva um programa Python, usando estrutura de sequência, que:

1. Peça ao usuário o preço de um produto e a quantidade comprada; *(0,5 pt)*
2. Calcule o valor total da compra; *(0,25 pt)*
3. Verifique (usando uma expressão relacional) se o valor total é maior ou igual a R$ 100,00; *(0,5 pt)*
4. Exiba o valor total e o resultado dessa verificação. *(0,25 pt)*

```python
preco = float(input("Digite o preço do produto: R$ "))
quantidade = int(input("Digite a quantidade: "))

total = preco * quantidade
frete_gratis = total >= 100.00

print("Valor total: R$", total)
print("Atinge R$ 100,00?", frete_gratis)
```
