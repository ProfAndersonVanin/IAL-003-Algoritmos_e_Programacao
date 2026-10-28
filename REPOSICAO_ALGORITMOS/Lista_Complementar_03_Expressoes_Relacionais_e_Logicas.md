# Lista Complementar 3 — Expressões Relacionais e Lógicas

**Disciplina:** IAL-003 – Algoritmos e Programação de Computadores
**Curso:** Informática para Negócios — Fatec Mauá
**Professor:** Anderson Silva Vanin
**Ambiente:** Google Colab | **Linguagem:** Python 3

---

## Orientações

Atividade **complementar** para fixação do conteúdo da **Aula 4**: operadores `==`, `!=`, `>`, `<`, `>=`, `<=`, `and`, `or`, `not` e estrutura de sequência.

- Resolva **um exercício por célula de código** e escreva comentários (`#`) nos trechos principais;
- Use **apenas** o conteúdo já estudado (sem funções criadas com `def` e sem laços `while`/`for`);
- Teste cada programa com **mais de um valor** de entrada;
- Os exemplos mostram o comportamento esperado — as mensagens podem ser escritas com suas palavras;
- Nível: ★ básico · ★★ intermediário.

> 💡 **Entrega:** salve seu notebook no Google Drive (*Arquivo → Salvar uma cópia no Drive*) com o
> nome `ListaComplementar3_SeuNome.ipynb` e envie o link conforme orientação do professor.

---

## Exercício 1 — Comparando dois números ★

Peça **dois números** e exiba o resultado (`True` ou `False`) das seis comparações: `==`, `!=`, `>`, `<`, `>=` e `<=`.

**Exemplo de execução:**
```
Primeiro número: 10
Segundo número: 7
== False
!= True
> True
< False
>= True
<= False
```

## Exercício 2 — Pode dirigir? ★

Peça a **idade** e se a pessoa possui **carteira** (`s`/`n`). Exiba `True` se ela pode dirigir (tem 18 anos ou mais **e** possui carteira) e `False` caso contrário.

**Exemplo de execução:**
```
Idade: 20   Carteira: s   →   Pode dirigir: True
Idade: 17   Carteira: s   →   Pode dirigir: False
```

## Exercício 3 — Aprovado? ★★

Peça **duas notas** e a **frequência** (em %). Calcule a média e exiba `True` se o aluno está aprovado (média **maior ou igual a 6** **e** frequência **maior ou igual a 75**).

**Exemplo de execução:**
```
Notas: 7 e 5   Frequência: 80   →   Média: 6.0   |   Aprovado: True
```

## Exercício 4 — Frete grátis ★★

Peça o **valor da compra** e se o cliente tem **cupom** (`s`/`n`). Exiba `True` se o frete é grátis (compra de **R$ 150,00 ou mais** **ou** cliente com cupom).

**Exemplo de execução:**
```
Valor: 120   Cupom: n   →   False
Valor: 120   Cupom: s   →   True
Valor: 150   Cupom: n   →   True
```

## Exercício 5 — Prevendo resultados ★★

Considere `a = 5`, `b = 10` e `c = 15`. **Antes de executar**, anote se cada expressão resulta em `True` ou `False`. Depois confira no Python e corrija suas previsões.

a) `a < b and b < c`
b) `a > b or c > b`
c) `not (a == 5)`
d) `(a + b == c) and (c - b == a)`
e) `not (a > b) or c < a`
