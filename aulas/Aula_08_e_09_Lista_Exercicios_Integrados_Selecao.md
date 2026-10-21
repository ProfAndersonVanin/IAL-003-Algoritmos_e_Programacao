# Lista de Exercícios Integrados — Estruturas de Seleção

**Disciplina:** IAL-003 – Algoritmos e Programação de Computadores
**Curso:** Informática para Negócios — Fatec Mauá
**Professor:** Anderson Silva Vanin
**Ambiente:** Google Colab | **Linguagem:** Python 3

---

## Orientações

Esta lista **integra todo o conteúdo estudado até aqui**: entrada de dados (`input()`), tipos de dados e
conversão, operadores aritméticos, expressões relacionais e lógicas e as estruturas de seleção
(`if`, `if/else` e `if/elif/else`).

**Regras da lista:**

- Use **apenas** o conteúdo já estudado. **Não use funções criadas por você (`def`) nem laços de
  repetição (`while`/`for`)** — esses assuntos virão depois;
- Teste cada programa com **vários valores de entrada**, incluindo os casos extremos (valores nos
  limites das faixas, zero, entradas inválidas);
- Os exemplos de execução mostram **como o programa deve se comportar**; as mensagens podem ser
  escritas com suas próprias palavras;
- Resolva um exercício por célula de código e escreva comentários (`#`) explicando as partes
  principais;
- Nível de dificuldade: ★ básico · ★★ intermediário · ★★★ desafio.

> 💡 **Entrega:** salve seu notebook no Google Drive (*Arquivo → Salvar uma cópia no Drive*) com o
> nome `ListaIntegrada_SeuNome.ipynb` e envie o link conforme orientação do professor.

---

## Exercício 1 — Maior de três números ★

Peça ao usuário **três números inteiros** e exiba qual deles é o maior.

**Exemplo de execução:**
```
Primeiro número: 7
Segundo número: 12
Terceiro número: 5
O maior número é 12
```

*Pense nos casos de empate: o programa não pode "travar" se dois números forem iguais.*

## Exercício 2 — Classificação de um número ★

Peça um número inteiro e exiba **duas informações**: se ele é **par** ou **ímpar** e se é
**positivo**, **negativo** ou **zero**.

**Exemplos de execução:**
```
Digite um número: -4            Digite um número: 0
Par                             Par
Negativo                        Zero
```

## Exercício 3 — Situação do aluno ★★

Peça **três notas** e a **frequência** (em %) de um aluno. Calcule a média aritmética e exiba a situação:

- Frequência **menor que 75%** → "Reprovado por falta" (independentemente da média);
- Caso contrário: média **maior ou igual a 6** → "Aprovado"; média **de 4 até menos de 6** →
  "Recuperação"; média **menor que 4** → "Reprovado por nota".

**Exemplos de execução:**
```
Notas: 7, 8, 6  | Frequência: 80   →   Média: 7.0  | Aprovado
Notas: 5, 6, 4  | Frequência: 90   →   Média: 5.0  | Recuperação
Notas: 9, 9, 9  | Frequência: 60   →   Reprovado por falta
```

## Exercício 4 — Calculadora com operador ★★

Peça **dois números** e um **operador** digitado pelo usuário (`+`, `-`, `*` ou `/`). Exiba o
resultado da operação. Trate dois casos especiais:

- **Divisão por zero:** exiba uma mensagem de erro em vez de calcular;
- **Operador inválido:** exiba "Operador inválido".

**Exemplos de execução:**
```
Número 1: 10    Número 2: 4    Operador: /    →   Resultado: 2.5
Número 1: 5     Número 2: 0    Operador: /    →   Não é possível dividir por zero
Número 1: 3     Número 2: 2    Operador: %    →   Operador inválido
```

## Exercício 5 — IMC e classificação ★★

Peça o **peso (kg)** e a **altura (m)**, calcule o IMC (`peso / altura ** 2`) e classifique:

| IMC | Classificação |
|---|---|
| Menor que 18,5 | Abaixo do peso |
| De 18,5 até menos de 25 | Peso normal |
| De 25 até menos de 30 | Sobrepeso |
| 30 ou mais | Obesidade |

Exiba o IMC (dica: `round(imc, 2)` arredonda para duas casas decimais) e a classificação.

**Exemplo de execução:**
```
Peso: 70    Altura: 1.75    →   IMC: 22.86  |  Peso normal
```

## Exercício 6 — Ano bissexto ★★

Peça um **ano** e informe se ele é bissexto. Um ano é bissexto quando é **divisível por 4** e **não é
divisível por 100**, **ou** quando é **divisível por 400**.

**Exemplos de execução:**
```
2024   →   Ano bissexto
1900   →   Ano não bissexto
2000   →   Ano bissexto
```

*Dica: use o operador `%` e combine as condições com `and` e `or` (cuidado com os parênteses).*

## Exercício 7 — Triângulos ★★★

Peça as medidas dos **três lados** de um triângulo. Primeiro verifique se eles **formam** um
triângulo: isso só acontece quando **cada lado é menor que a soma dos outros dois**. Se formarem,
classifique o triângulo:

- **Equilátero:** os três lados iguais;
- **Isósceles:** exatamente dois lados iguais;
- **Escaleno:** os três lados diferentes.

**Exemplos de execução:**
```
3, 3, 3    →   Triângulo equilátero
3, 3, 5    →   Triângulo isósceles
3, 4, 5    →   Triângulo escaleno
1, 2, 10   →   Essas medidas não formam um triângulo
```

## Exercício 8 — Compra com desconto, cupom e frete ★★★

Peça o **valor da compra** e se o cliente possui **cupom** (`s`/`n`). Aplique as regras na ordem:

1. **Desconto percentual** sobre o valor original: compras **abaixo de R$ 100** → sem desconto; de
   **R$ 100 até R$ 299,99** → 5%; a partir de **R$ 300** → 10%;
2. Se o cliente tem **cupom**, subtraia mais **R$ 20,00** do valor já com desconto (o valor nunca pode
   ficar negativo);
3. **Frete grátis** se o valor final for **maior ou igual a R$ 150,00**; caso contrário, o frete é de
   **R$ 15,00**.

Exiba o valor final dos produtos e o frete.

**Exemplos de execução:**
```
Valor: 250    Cupom: s   →   Valor com descontos: R$ 217.5   |   Frete: grátis
Valor: 80     Cupom: n   →   Valor com descontos: R$ 80.0    |   Frete: R$ 15.00
```

## Exercício 9 — Caixa eletrônico ★★★

Peça o **saldo** da conta e o **valor do saque**. Valide, **nesta ordem**:

1. O valor do saque deve ser **maior que zero**, caso contrário → "Valor inválido";
2. O valor deve ser **múltiplo de 10** (notas disponíveis), caso contrário → "O valor deve ser múltiplo
   de 10";
3. O valor não pode ser **maior que o saldo**, caso contrário → "Saldo insuficiente".

Se passar nas três validações, exiba "Saque realizado" e o **novo saldo**.

**Exemplos de execução (saldo 500):**
```
Saque 120   →   Saque realizado. Novo saldo: 380
Saque 125   →   O valor deve ser múltiplo de 10
Saque 600   →   Saldo insuficiente
Saque -10   →   Valor inválido
```

## Exercício 10 — Pedra, papel e tesoura ★★★ (desafio)

Dois jogadores digitam suas jogadas (`pedra`, `papel` ou `tesoura`). Exiba o resultado da partida:

- Jogadas **iguais** → "Empate";
- Pedra vence tesoura; tesoura vence papel; papel vence pedra;
- Se algum dos jogadores digitar uma jogada que não existe → "Jogada inválida".

**Exemplos de execução:**
```
Jogador 1: pedra    Jogador 2: tesoura   →   Jogador 1 vence!
Jogador 1: papel    Jogador 2: papel     →   Empate
Jogador 1: fogo     Jogador 2: pedra     →   Jogada inválida
```

*Dica: valide as jogadas primeiro; depois verifique o empate; por fim, use `and`/`or` para identificar as
combinações em que o jogador 1 vence.*

---
