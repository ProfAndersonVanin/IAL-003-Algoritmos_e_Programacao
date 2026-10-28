# Lista Complementar 2 — Operadores Aritméticos e Precedência

**Disciplina:** IAL-003 – Algoritmos e Programação de Computadores
**Curso:** Informática para Negócios — Fatec Mauá
**Professor:** Anderson Silva Vanin
**Ambiente:** Google Colab | **Linguagem:** Python 3

---

## Orientações

Atividade **complementar** para fixação do conteúdo da **Aula 3**: operadores `+`, `-`, `*`, `/`, `//`, `%`, `**`, precedência e parênteses.

- Resolva **um exercício por célula de código** e escreva comentários (`#`) nos trechos principais;
- Use **apenas** o conteúdo já estudado (sem funções criadas com `def` e sem laços `while`/`for`);
- Teste cada programa com **mais de um valor** de entrada;
- Os exemplos mostram o comportamento esperado — as mensagens podem ser escritas com suas palavras;
- Nível: ★ básico · ★★ intermediário.

> 💡 **Entrega:** salve seu notebook no Google Drive (*Arquivo → Salvar uma cópia no Drive*) com o
> nome `ListaComplementar2_SeuNome.ipynb` e envie o link conforme orientação do professor.

---

## Exercício 1 — As quatro operações ★

Peça **dois números** (`float`) e exiba o resultado da soma, subtração, multiplicação e divisão entre eles.

**Exemplo de execução:**
```
Primeiro número: 10
Segundo número: 4
Soma: 14.0
Subtração: 6.0
Multiplicação: 40.0
Divisão: 2.5
```

## Exercício 2 — Média de três notas ★

Peça **três notas** e exiba a média aritmética. Atenção à precedência: a soma precisa estar entre parênteses.

**Exemplo de execução:**
```
Notas: 7, 8 e 9   →   Média: 8.0
```

## Exercício 3 — Minutos em horas ★★

Peça uma quantidade de **minutos** e exiba quantas **horas** e quantos **minutos restantes** isso representa, usando `//` e `%`.

**Exemplo de execução:**
```
Minutos: 130
2 hora(s) e 10 minuto(s)
```

## Exercício 4 — Áreas e perímetro ★★

Peça a **base** e a **altura** de um retângulo e exiba a **área** e o **perímetro**. Em seguida, peça o **raio** de um círculo e exiba a área (use `3.14159` para π).

**Exemplo de execução:**
```
Base: 5   Altura: 3   →   Área: 15.0   |   Perímetro: 16.0
Raio: 2   →   Área do círculo: 12.56636
```

## Exercício 5 — Precedência na prática ★★

**Antes de executar**, resolva no papel cada expressão abaixo, seguindo a ordem de precedência. Depois confira os resultados no Python (usando `print()`) e corrija suas previsões, se necessário.

a) `8 / 2 * 4`
b) `8 / (2 * 4)`
c) `7 + 3 * 2 ** 2`
d) `(7 + 3) * 2 ** 2`
e) `17 % 5 + 17 // 5`
