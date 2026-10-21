# IAL-003 – Algoritmos e Programação de Computadores
## Aula 7 — Estruturas de Seleção Simples (`if`) e Composta (`if/else`)

**Curso:** Informática para Negócios — Fatec Mauá
**Professor:** Anderson Silva Vanin
**Ambiente:** Google Colab | **Linguagem:** Python 3

---

## 1. Recapitulando as aulas anteriores

Até aqui, todos os programas que escrevemos eram **sequenciais**: o Python executava cada linha, de
cima para baixo, **sempre na mesma ordem e sem pular nenhuma instrução**.

Já aprendemos as ferramentas necessárias para tomar decisões:

- **Expressões relacionais** (`==`, `!=`, `>`, `<`, `>=`, `<=`) comparam valores e resultam em `bool`;
- **Expressões lógicas** (`and`, `or`, `not`) combinam condições;
- `input()` captura dados do usuário (sempre como `str`) e `int()`/`float()` convertem o valor.

O que ainda falta é **usar o resultado `True`/`False` para decidir o que o programa faz**. É isso que as
estruturas de seleção permitem.

```python
# Relembrando: uma comparação resulta em True ou False
idade = 20
print(idade >= 18)

maior_de_idade = idade >= 18
print("Maior de idade?", maior_de_idade)
```

## 2. Tomada de decisão: o fluxo condicional

No dia a dia tomamos decisões o tempo todo: *"se estiver chovendo, levo o guarda-chuva"*; *"se o saldo
for suficiente, faço a compra; senão, desisto"*. Em algoritmos, isso é chamado de **estrutura de
seleção** (ou **estrutura condicional**): o programa avalia uma **condição** e, de acordo com o resultado
(`True` ou `False`), escolhe qual caminho seguir.

Em **pseudocódigo**, uma seleção simples e uma composta ficam assim:

```
SE chover ENTÃO                    SE saldo >= valor ENTÃO
    levar guarda-chuva                 realizar compra
FIM-SE                             SENÃO
                                       exibir "saldo insuficiente"
                                   FIM-SE
```

## 3. Seleção simples: `if`

A seleção simples executa um bloco de instruções **somente se** a condição for verdadeira. Se for falsa,
o bloco é ignorado e o programa segue adiante.

```python
if condição:
    instrução 1      # bloco executado apenas se a condição for True
    instrução 2
```

**Pontos de atenção na sintaxe:**

- `if` é uma palavra reservada, e a **condição** é qualquer expressão que resulte em `bool`;
- Os **dois-pontos (`:`)** ao final da linha do `if` são obrigatórios;
- A **indentação** (recuo de 4 espaços) define o que pertence ao bloco do `if`. Em Python não existem
  chaves `{}` — é o recuo que marca o início e o fim do bloco.

```python
idade = int(input("Digite sua idade: "))

if idade >= 18:
    print("Você é maior de idade.")

print("Fim do programa.")   # sem recuo: executa SEMPRE, independentemente do if
```

Execute a célula acima duas vezes: uma digitando uma idade **maior ou igual a 18** e outra com uma idade
**menor**. Observe que a mensagem de maior de idade só aparece no primeiro caso, mas "Fim do programa."
aparece nos dois — porque não está dentro do bloco do `if`.

O bloco do `if` pode ter **várias instruções**, todas com o mesmo recuo:

```python
valor = float(input("Valor da compra: R$ "))

if valor >= 200:
    desconto = valor * 0.10
    valor = valor - desconto
    print("Desconto de 10% aplicado!")

print("Total a pagar: R$", valor)
```

## 4. Seleção composta: `if/else`

A seleção composta oferece **dois caminhos**: um bloco para quando a condição é verdadeira e outro
(`else`) para quando é falsa. **Exatamente um** dos dois blocos é executado — nunca os dois, nunca
nenhum.

```python
if condição:
    bloco executado se for True
else:
    bloco executado se for False
```

O `else` **não tem condição** — ele representa "todos os outros casos" — e também termina com `:`.

```python
numero = int(input("Digite um número inteiro: "))

if numero % 2 == 0:
    print(numero, "é par.")
else:
    print(numero, "é ímpar.")
```

```python
nota1 = float(input("Digite a primeira nota: "))
nota2 = float(input("Digite a segunda nota: "))

media = (nota1 + nota2) / 2

if media >= 6:
    print("Aprovado!")
else:
    print("Reprovado.")

print("Média final:", media)
```

Também é possível comparar **textos** (`str`) dentro do `if`. Lembre-se de que o Python diferencia
maiúsculas de minúsculas:

```python
senha_correta = "fatec2026"
senha = input("Digite a senha: ")

if senha == senha_correta:
    print("Acesso liberado.")
else:
    print("Senha incorreta.")
```

## 5. Condições compostas (`and`, `or`, `not`) dentro do `if`

Na Aula 4 aprendemos a combinar condições com `and`, `or` e `not`. Agora podemos usá-las diretamente
dentro do `if`, para decisões que dependem de mais de um critério.

Um truque útil: uma comparação feita sobre o `input()` já resulta em `bool`, e pode ser guardada em uma
variável.

```python
idade = int(input("Idade: "))
tem_carteira = input("Possui carteira de motorista? (s/n): ") == "s"

if idade >= 18 and tem_carteira:
    print("Pode dirigir.")
else:
    print("Não pode dirigir.")
```

```python
dia_util = input("Hoje é dia útil? (s/n): ") == "s"
tem_cupom = input("Possui cupom? (s/n): ") == "s"

if dia_util or tem_cupom:
    print("Você tem direito ao desconto.")
else:
    print("Sem desconto hoje.")
```

> 💡 Assim como nas expressões aritméticas, **use parênteses** quando misturar `and` e `or`, para
> deixar claro como a condição deve ser lida: `if (idade >= 18 and tem_ingresso) or esta_na_lista:`.

## 6. Estruturas aninhadas

Dentro de um bloco de `if` (ou de `else`) podemos colocar **outro `if`**. Isso é chamado de
**aninhamento**: a segunda decisão só é avaliada se a primeira condição levar até ela. Cada nível de
aninhamento recebe **mais um recuo**.

```python
numero = float(input("Digite um número: "))

if numero >= 0:
    if numero == 0:
        print("O número é zero.")
    else:
        print("O número é positivo.")
else:
    print("O número é negativo.")
```

Funciona, mas repare que, com **três ou mais caminhos**, o código vai ficando cheio de recuos e mais
difícil de ler. Na próxima aula veremos o `elif`, que resolve esse problema de forma muito mais limpa.

## 7. Erros comuns

| Erro | Exemplo incorreto | Forma correta |
|---|---|---|
| Usar `=` (atribuição) no lugar de `==` (comparação) | `if idade = 18:` | `if idade == 18:` |
| Esquecer os dois-pontos | `if idade >= 18` | `if idade >= 18:` |
| Esquecer a indentação do bloco | `if x > 0:` seguido de `print(...)` sem recuo (gera `IndentationError`) | `print(...)` com 4 espaços de recuo |
| Comparar `input()` sem converter | `if input("Idade: ") >= 18:` (compara `str` com `int` e gera `TypeError`) | `idade = int(input("Idade: "))` e depois `if idade >= 18:` |
| Colocar condição no `else` | `else idade < 18:` | `else:` (o `else` nunca tem condição) |
| Misturar recuos diferentes no mesmo bloco | linhas com 2 e 4 espaços | manter sempre os mesmos 4 espaços |

## 8. Exercícios práticos

Resolva os exercícios abaixo no Colab. Teste cada programa **com pelo menos dois valores** diferentes,
para conferir que os dois caminhos do `if/else` funcionam.

### Exercício 1
Peça a idade do usuário. Se for maior ou igual a 18, exiba "Acesso permitido". Independentemente da
idade, exiba em seguida "Programa encerrado." (use apenas `if` simples).

### Exercício 2
Peça dois números ao usuário e exiba qual deles é o **maior**. Se forem iguais, exiba uma mensagem
informando que os números são iguais.

### Exercício 3
Peça o valor de uma compra e se o cliente possui cartão fidelidade (`s`/`n`). O cliente ganha **5% de
desconto** somente se tiver o cartão **e** a compra for de pelo menos R$ 100,00. Exiba o valor final.

### Exercício 4
Crie um "login" simples: defina no código um usuário e uma senha corretos, peça ao usuário que digite
os dois e exiba "Bem-vindo!" se **ambos** estiverem corretos, ou "Usuário ou senha inválidos." caso
contrário.

### Exercício 5 (desafio)
Peça um número inteiro e informe se ele é divisível por 3 **e** por 5 ao mesmo tempo, apenas por um
dos dois, ou por nenhum. Use `if` aninhado (na próxima aula você verá uma forma mais simples).

> 💡 **Entrega:** salve seu notebook no Google Drive (*Arquivo → Salvar uma cópia no Drive*) com o
> nome `Aula07_SeuNome.ipynb` e envie o link conforme orientação do professor.

## Resumo da aula

- As **estruturas de seleção** permitem que o programa escolha qual caminho seguir, de acordo com uma
  condição (`True` ou `False`).
- `if` (seleção simples) executa um bloco **apenas se** a condição for verdadeira.
- `if/else` (seleção composta) executa **exatamente um** de dois blocos.
- Em Python, o **recuo (indentação)** e os **dois-pontos (`:`)** são obrigatórios e definem os blocos.
- Condições podem ser combinadas com `and`, `or` e `not`, e um `if` pode ser **aninhado** dentro de outro.

## Para a próxima aula
Vamos estudar a **seleção múltipla com `elif`**, usada quando há mais de dois caminhos possíveis, e
praticar com exercícios.
