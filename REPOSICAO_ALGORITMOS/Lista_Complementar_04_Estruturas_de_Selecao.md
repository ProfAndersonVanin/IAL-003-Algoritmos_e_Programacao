# Lista Complementar 4 — Estruturas de Seleção (`if`, `else` e `elif`)

**Disciplina:** IAL-003 – Algoritmos e Programação de Computadores
**Curso:** Informática para Negócios — Fatec Mauá
**Professor:** Anderson Silva Vanin
**Ambiente:** Google Colab | **Linguagem:** Python 3

---

## Orientações

Atividade **complementar** para fixação do conteúdo das **Aulas 7 e 8**: `if`, `if/else`, `if/elif/else` e condições compostas.

- Resolva **um exercício por célula de código** e escreva comentários (`#`) nos trechos principais;
- Use **apenas** o conteúdo já estudado (sem funções criadas com `def` e sem laços `while`/`for`);
- Teste cada programa com **mais de um valor** de entrada;
- Os exemplos mostram o comportamento esperado — as mensagens podem ser escritas com suas palavras;
- Nível: ★ básico · ★★ intermediário.

> 💡 **Entrega:** salve seu notebook no Google Drive (*Arquivo → Salvar uma cópia no Drive*) com o
> nome `ListaComplementar4_SeuNome.ipynb` e envie o link conforme orientação do professor.

---

## Exercício 1 — Maior ou menor de idade ★

Peça a **idade** e exiba "Maior de idade" se for 18 ou mais; caso contrário, exiba "Menor de idade".

**Exemplo de execução:**
```
Idade: 20   →   Maior de idade
Idade: 15   →   Menor de idade
```

## Exercício 2 — Par ou ímpar ★

Peça um **número inteiro** e exiba se ele é **par** ou **ímpar** (use o operador `%`).

**Exemplo de execução:**
```
Número: 8   →   Par
Número: 7   →   Ímpar
```

## Exercício 3 — Positivo, negativo ou zero ★★

Peça um **número** e exiba se ele é **positivo**, **negativo** ou **zero**.

**Exemplo de execução:**
```
Número: -5   →   Negativo
Número: 0    →   Zero
Número: 3    →   Positivo
```

## Exercício 4 — Desconto por quantidade ★★

Peça o **preço unitário** e a **quantidade** comprada. Aplique o desconto sobre o total: de **1 a 9** unidades → sem desconto; de **10 a 49** → 5%; **50 ou mais** → 10%. Se a quantidade for menor que 1, exiba "Quantidade inválida". Caso contrário, exiba o total a pagar.

**Exemplo de execução:**
```
Preço: 10   Quantidade: 20   →   Total: R$ 190.0
Preço: 10   Quantidade: 5    →   Total: R$ 50.0
Preço: 10   Quantidade: 0    →   Quantidade inválida
```

## Exercício 5 — Semáforo ★★

Peça a **cor** do semáforo (`verde`, `amarelo` ou `vermelho`, em minúsculas) e exiba a orientação: verde → "Pode seguir"; amarelo → "Atenção, reduza a velocidade"; vermelho → "Pare". Para qualquer outra cor, exiba "Cor inválida".

**Exemplo de execução:**
```
Cor: verde      →   Pode seguir
Cor: vermelho   →   Pare
Cor: azul       →   Cor inválida
```
