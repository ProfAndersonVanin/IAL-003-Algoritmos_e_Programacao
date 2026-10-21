# IAL-003 – Algoritmos e Programação de Computadores
## Aula 8 — Estruturas de Seleção Múltipla (`elif`) e Exercícios Práticos

**Curso:** Informática para Negócios — Fatec Mauá
**Professor:** Anderson Silva Vanin
**Ambiente:** Google Colab | **Linguagem:** Python 3

---

## 1. Recapitulando a Aula 7

Na aula passada vimos que:

- `if` executa um bloco **somente se** a condição for verdadeira;
- `if/else` escolhe **entre dois caminhos**;
- A indentação e os dois-pontos (`:`) definem os blocos;
- Um `if` pode ser aninhado dentro de outro — mas, com muitos caminhos, o código fica cheio de recuos.

Veja o problema: classificar uma nota em quatro conceitos usando apenas `if/else` aninhados.

```python
nota = float(input("Digite a nota (0 a 10): "))

if nota >= 9:
    conceito = "A"
else:
    if nota >= 7:
        conceito = "B"
    else:
        if nota >= 5:
            conceito = "C"
        else:
            conceito = "D"

print("Conceito:", conceito)
```

Funciona, mas é difícil de ler: cada novo caminho exige mais um recuo. O `elif` resolve exatamente isso.

## 2. Seleção múltipla: `if/elif/else`

O `elif` (contração de *else if*, "senão se") permite encadear **vários caminhos** no mesmo nível de
recuo:

```python
if condição1:
    bloco 1
elif condição2:
    bloco 2
elif condição3:
    bloco 3
else:
    bloco executado se nenhuma condição anterior for verdadeira
```

**Como o Python executa:**

1. Testa as condições **de cima para baixo**;
2. Ao encontrar a **primeira** condição verdadeira, executa o bloco dela e **ignora todo o restante**;
3. Se nenhuma for verdadeira, executa o `else` (que é **opcional**);
4. Podemos usar quantos `elif` forem necessários.

```python
nota = float(input("Digite a nota (0 a 10): "))

if nota >= 9:
    conceito = "A"
elif nota >= 7:
    conceito = "B"
elif nota >= 5:
    conceito = "C"
else:
    conceito = "D"

print("Conceito:", conceito)
```

> 💡 Repare que no `elif nota >= 7` **não precisamos escrever** `and nota < 9`: se o programa chegou
> nessa linha, é porque `nota >= 9` já foi falso. Cada `elif` só é testado quando todas as condições
> anteriores falharam.

Mais um exemplo, retomando o IMC da Aula 4, agora classificando o resultado:

```python
peso = float(input("Peso (kg): "))
altura = float(input("Altura (m): "))

imc = peso / (altura ** 2)
print("IMC:", round(imc, 2))

if imc < 18.5:
    print("Abaixo do peso")
elif imc < 25:
    print("Peso normal")
elif imc < 30:
    print("Sobrepeso")
else:
    print("Obesidade")
```

> `round(imc, 2)` é uma função pronta do Python que arredonda o número para 2 casas decimais.

E um exemplo em que cada `elif` compara com um **valor exato** (número de 1 a 7 → dia da semana):

```python
numero = int(input("Digite um número de 1 a 7: "))

if numero == 1:
    print("Domingo")
elif numero == 2:
    print("Segunda-feira")
elif numero == 3:
    print("Terça-feira")
elif numero == 4:
    print("Quarta-feira")
elif numero == 5:
    print("Quinta-feira")
elif numero == 6:
    print("Sexta-feira")
elif numero == 7:
    print("Sábado")
else:
    print("Número inválido!")
```

## 3. A ordem das condições importa

Como o Python para na **primeira** condição verdadeira, a ordem em que escrevemos as condições muda o
resultado. Veja o que acontece quando colocamos a condição **mais abrangente** primeiro:

```python
nota = 9.5

# ORDEM ERRADA: a primeira condição (nota >= 5) já é verdadeira para 9.5
if nota >= 5:
    print("Conceito C")
elif nota >= 7:
    print("Conceito B")
elif nota >= 9:
    print("Conceito A")
```

Uma nota 9.5 recebeu o conceito **C**! Isso acontece porque `9.5 >= 5` é verdadeiro e o Python nem chega
a testar as outras condições. Quando as faixas são "maior ou igual a", comece sempre pela **mais
restritiva** (a maior); quando são "menor que", comece pela menor.

## 4. `elif` ou vários `if` independentes?

Escrever vários `if` **seguidos** não é o mesmo que usar `elif`. Cada `if` independente é avaliado
sempre, mesmo que um anterior já tenha sido verdadeiro.

```python
idade = 20

# Vários if independentes: TODAS as condições verdadeiras executam
if idade >= 18:
    print("Pode votar")
if idade >= 16:
    print("Pode votar (facultativo)")
if idade >= 0:
    print("Tem idade válida")
```

```python
idade = 20

# Com elif: somente o PRIMEIRO caminho verdadeiro executa
if idade >= 18:
    print("Pode votar (obrigatório)")
elif idade >= 16:
    print("Pode votar (facultativo)")
else:
    print("Não pode votar")
```

**Regra prática:** use `elif` quando os casos são **mutuamente exclusivos** (só um pode valer, como as
faixas de uma nota). Use `if` separados quando as verificações são **independentes** (várias podem
valer ao mesmo tempo).

## 5. Menus de opções

O `elif` é ideal para **menus**: o usuário escolhe uma opção e o programa executa o trecho
correspondente. Lembre-se de que `input()` devolve `str`, então comparamos com textos (`"1"`, `"2"`...).

```python
a = float(input("Primeiro número: "))
b = float(input("Segundo número: "))

print("1 - Somar")
print("2 - Subtrair")
print("3 - Multiplicar")
print("4 - Dividir")
opcao = input("Escolha uma opção: ")

if opcao == "1":
    print("Resultado:", a + b)
elif opcao == "2":
    print("Resultado:", a - b)
elif opcao == "3":
    print("Resultado:", a * b)
elif opcao == "4":
    if b == 0:
        print("Não é possível dividir por zero.")
    else:
        print("Resultado:", a / b)
else:
    print("Opção inválida.")
```

Observe o `if/else` aninhado dentro da opção 4, tratando a divisão por zero: aninhar continua sendo útil
quando uma escolha tem uma verificação **extra** dentro dela.

## 6. Para ir além: `match-case`

A partir do Python 3.10 (disponível no Colab), existe uma alternativa ao `elif` para comparar uma
variável com **valores exatos**: o `match-case`. O caso `_` funciona como o `else`.

> Neste curso, usaremos principalmente `if/elif/else`, que funciona em qualquer versão do Python. O
> `match-case` é apresentado só para você conhecer.

```python
opcao = input("Escolha 1, 2 ou 3: ")

match opcao:
    case "1":
        print("Você escolheu a opção 1")
    case "2":
        print("Você escolheu a opção 2")
    case "3":
        print("Você escolheu a opção 3")
    case _:
        print("Opção inválida")
```

## 7. Erros comuns

| Erro | Problema | Como evitar |
|---|---|---|
| Faixas na ordem errada | A condição mais abrangente "engole" as outras (como a nota 9.5 virando conceito C) | Comece pela condição mais restritiva |
| Usar `if` no lugar de `elif` | Vários blocos executam quando só um deveria | Use `elif` para casos mutuamente exclusivos |
| Faixas com "buracos" | `nota > 7` e `nota < 7` deixam o valor 7 de fora | Use `>=` ou `<=` em um dos lados |
| Esquecer o `else` para entradas inválidas | Opção inesperada passa sem nenhuma mensagem | Use `else` como "rede de segurança" |
| Comparar `input()` com número sem converter | `if opcao == 1:` nunca é verdadeiro, pois `opcao` é `str` | Compare com `"1"` ou converta com `int()` |
| Repetir a variável incorretamente | `elif nota >= 7 and <= 9:` (sintaxe inválida) | Escreva `elif nota >= 7:` ou `elif 7 <= nota < 9:` |

## 8. Exercícios práticos

### Exercício 1
Peça a idade e classifique a pessoa: menor de 12 anos → **criança**; de 12 a 17 → **adolescente**; de
18 a 59 → **adulto**; 60 ou mais → **idoso**.

### Exercício 2
Peça um número de 1 a 12 e exiba o **nome do mês** correspondente. Para qualquer outro número, exiba
"Mês inválido".

### Exercício 3
Peça o salário bruto de um funcionário e calcule o desconto de um imposto **fictício** com as faixas:

| Salário bruto | Alíquota |
|---|---|
| Até R$ 2.000,00 | Isento |
| De R$ 2.000,01 até R$ 4.000,00 | 10% |
| De R$ 4.000,01 até R$ 8.000,00 | 15% |
| Acima de R$ 8.000,00 | 20% |

Exiba o valor do imposto e o salário líquido.

### Exercício 4
Crie um **conversor de temperatura** com menu: `1` - Celsius para Fahrenheit; `2` - Fahrenheit para
Celsius; `3` - Celsius para Kelvin. Peça a opção e o valor e exiba o resultado. Para opção inválida,
exiba uma mensagem.

Fórmulas: `F = C * 9 / 5 + 32`, `C = (F - 32) * 5 / 9`, `K = C + 273.15`.

### Exercício 5 (desafio)
Faça um **quiz de três perguntas** (de múltipla escolha com respostas `a`, `b` ou `c`) sobre o que já
estudamos em Python. Comece com `pontos = 0` e some 1 ponto a cada resposta certa (`pontos = pontos + 1`
dentro de um `if`). Ao final, exiba: 0 ou 1 ponto → "Precisa estudar mais"; 2 pontos → "Bom"; 3 pontos →
"Excelente!".

> 💡 **Entrega:** salve seu notebook no Google Drive (*Arquivo → Salvar uma cópia no Drive*) com o
> nome `Aula08_SeuNome.ipynb` e envie o link conforme orientação do professor.

## Resumo da aula

- `elif` permite **vários caminhos** no mesmo nível de recuo, sem aninhar `if` dentro de `else`.
- O Python testa as condições **de cima para baixo** e executa **apenas o primeiro** bloco verdadeiro.
- A **ordem** das condições importa: comece pela mais restritiva.
- Use `elif` para casos **mutuamente exclusivos** e `if` separados para verificações independentes.
- `elif` é ideal para **menus** e para **classificação por faixas**; o `else` final cuida dos casos
  inesperados.

## Para a próxima atividade
Na sequência, vamos resolver a **Lista de exercícios integrados** (10 exercícios), que reúne tudo o que
estudamos até aqui: entrada de dados, tipos, operadores, expressões lógicas e estruturas de seleção.
Depois dela, estudaremos **modularização com funções (`def`)**.
