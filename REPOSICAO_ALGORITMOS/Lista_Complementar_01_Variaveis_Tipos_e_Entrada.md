# Lista Complementar 1 — Variáveis, Tipos de Dados e Entrada de Dados

**Disciplina:** IAL-003 – Algoritmos e Programação de Computadores
**Curso:** Informática para Negócios — Fatec Mauá
**Professor:** Anderson Silva Vanin
**Ambiente:** Google Colab | **Linguagem:** Python 3

---

## Orientações

Atividade **complementar** para fixação do conteúdo das **Aulas 1 e 2**: `print()`, variáveis, tipos (`int`, `float`, `str`, `bool`), `type()`, conversão de tipos e `input()`.

- Resolva **um exercício por célula de código** e escreva comentários (`#`) nos trechos principais;
- Use **apenas** o conteúdo já estudado (sem funções criadas com `def` e sem laços `while`/`for`);
- Teste cada programa com **mais de um valor** de entrada;
- Os exemplos mostram o comportamento esperado — as mensagens podem ser escritas com suas palavras;
- Nível: ★ básico · ★★ intermediário.

> 💡 **Entrega:** salve seu notebook no Google Drive (*Arquivo → Salvar uma cópia no Drive*) com o
> nome `ListaComplementar1_SeuNome.ipynb` e envie o link conforme orientação do professor.

---

## Exercício 1 — Apresentação pessoal ★

Crie três variáveis (`nome`, `idade` e `cidade`) com os seus dados e exiba cada uma em uma linha, no formato do exemplo.

**Exemplo de execução:**
```
Nome: Ana
Idade: 20
Cidade: Mauá
```

## Exercício 2 — Descobrindo os tipos ★

Crie quatro variáveis, uma de cada tipo (`int`, `float`, `str` e `bool`), e exiba o **valor** e o **tipo** de cada uma usando `type()`.

**Exemplo de execução:**
```
10 <class 'int'>
3.5 <class 'float'>
Python <class 'str'>
True <class 'bool'>
```

## Exercício 3 — Boas-vindas personalizadas ★

Peça o **nome** e a **idade** do usuário e exiba uma mensagem informando quantos anos ele terá daqui a 5 anos.

**Exemplo de execução:**
```
Nome: Carlos
Idade: 30
Olá, Carlos! Daqui a 5 anos você terá 35 anos.
```

## Exercício 4 — Texto ou número? ★★

Peça **dois números** ao usuário. Exiba o resultado de somá-los **sem converter** os valores e, em seguida, **convertidos** para `int`. Escreva um comentário (`#`) explicando por que os resultados são diferentes.

**Exemplo de execução:**
```
Primeiro número: 3
Segundo número: 4
Sem conversão: 34
Com conversão: 7
```

## Exercício 5 — Ficha de produto ★★

Peça o **nome** do produto (`str`), o **preço** (`float`), a **quantidade** (`int`) e se está **disponível** (`s`/`n`, guardando o resultado da comparação em uma variável `bool`). Exiba cada informação seguida do seu tipo.

**Exemplo de execução:**
```
Produto: Caderno (str)
Preço: 12.5 (float)
Quantidade: 3 (int)
Disponível: True (bool)
```
