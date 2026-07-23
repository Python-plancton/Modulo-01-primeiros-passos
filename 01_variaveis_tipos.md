# 01 - Variáveis e Tipos

> Trilha Python para Dados · Módulo 01 - Primeiros Passos

Antes deste arquivo, leia [00_introducao_python.md](https://github.com/Python-plancton/modulo-01-primeiros-passos/blob/main/00_introducao_python.md). Depois de ler cada tópico
abaixo, abra `01_variaveis_tipos.ipynb` e resolva os exercícios daquele
tópico antes de seguir para o próximo.

---

## 1. Conceito de variável

Uma variável é um **espaço na memória do computador com um nome**, usado
para guardar um valor que pode ser lido ou alterado depois.

Pensa assim: uma variável é uma caixa com etiqueta. Você guarda algo dentro
dela e, sempre que precisar, chama pelo nome da etiqueta para usar o que
está guardado — sem precisar saber onde exatamente a caixa está na memória.

```python
idade = 25
nome = "Maria"
```

Aqui `idade` e `nome` são as etiquetas (nomes), e `25` e `"Maria"` são os
valores guardados.

### O que uma variável permite

- **Guardar** um valor para usar depois, sem repetir o valor várias vezes.
- **Reutilizar** o mesmo valor em vários pontos do código.
- **Alterar** o valor guardado ao longo da execução.
- **Dar significado** ao código (`preco_final` diz mais que `12.5` sozinho).

```python
preco = 100
desconto = 0.10
preco_final = preco - (preco * desconto)
print(preco_final)  # 90.0
```

Se `preco` mudar, `preco_final` pode ser recalculado sem reescrever a lógica
inteira, essa é a vantagem de nomear valores.

### Múltiplas atribuições

Em Python, é possível atribuir valores a várias variáveis em uma única linha.
Esse recurso torna o código mais conciso e é muito utilizado pela comunidade.

As duas formas abaixo são equivalentes:
```python
x = 10
y = 20

x, y = 10, 20
```
💡 Curiosidade

A atribuição múltipla também permite trocar os valores de duas variáveis sem precisar de uma variável auxiliar.
```python
x = 10
y = 20

x, y = y, x

print(x)  # 20
print(y)  # 10

```
Essa é uma característica bastante conhecida do Python e será útil em diversos exercícios ao longo da trilha.
---

## 2. Nomes de variáveis

Python tem regras obrigatórias e convenções recomendadas para nomear
variáveis.

### Regras obrigatórias (o código quebra se não seguir)

| Regra | Exemplo válido | Exemplo inválido |
|---|---|---|
| Pode conter letras, números e `_` | `total_2024` | — |
| Não pode começar com número | `valor1` | `1valor` |
| Não pode ter espaço | `nome_cliente` | `nome cliente` |
| Não pode ser palavra reservada | `classe` | `class` |
| É case sensitive (maiúscula ≠ minúscula) | `Idade` ≠ `idade` | — |

Palavras reservadas são termos que o próprio Python já usa, como `if`,
`for`, `class`, `True`, `import`. Não podem virar nome de variável.

### Convenção recomendada: snake_case

Em Python, o padrão da comunidade é escrever nomes de variáveis em
minúsculas, separando palavras com `_`:

```python
nome_completo = "Ana Souza"
data_nascimento = "1998-04-12"
total_de_vendas = 4500
```

Nomes devem ser **descritivos**. Prefira `preco_final` a `pf` ou `x`.

---

## 3. Variáveis numéricas

Python tem dois tipos numéricos principais para o dia a dia:

| Tipo | Representa | Exemplo |
|---|---|---|
| `int` | números inteiros | `10`, `-3`, `0` |
| `float` | números com casas decimais | `3.14`, `-0.5`, `10.0` |

```python
quantidade = 10        # int
temperatura = 36.5     # float
```

Repare que `10` é `int`, mas `10.0` é `float` - o ponto decimal muda o tipo,
mesmo que o valor "pareça" o mesmo número.

Você pode verificar o tipo de qualquer variável com `type()`:

```python
print(type(quantidade))    # <class 'int'>
print(type(temperatura))   # <class 'float'>
```

### Operadores aritméticos

| Operador | Operação | Exemplo | Resultado |
|---|---|---|---|
| `+` | soma | `5 + 2` | `7` |
| `-` | subtração | `5 - 2` | `3` |
| `*` | multiplicação | `5 * 2` | `10` |
| `/` | divisão (sempre retorna float) | `5 / 2` | `2.5` |
| `//` | divisão inteira (descarta o resto) | `5 // 2` | `2` |
| `%` | resto da divisão (módulo) | `5 % 2` | `1` |
| `**` | potência | `5 ** 2` | `25` |

```python
vendas_totais = 1500
meses = 4
media_mensal = vendas_totais / meses
print(media_mensal)  # 375.0
```

---

## 4. Variáveis do tipo lógico (bool)

O tipo `bool` guarda apenas dois valores possíveis: `True` ou `False`
(sempre com a primeira letra maiúscula). É o tipo usado para representar
decisões e comparações.

```python
ativo = True
inadimplente = False
print(type(ativo))  # <class 'bool'>
```

### Operadores relacionais

Comparam dois valores e o resultado é sempre um `bool`.

| Operador | Significado | Exemplo | Resultado |
|---|---|---|---|
| `==` | igual a | `5 == 5` | `True` |
| `!=` | diferente de | `5 != 3` | `True` |
| `>` | maior que | `5 > 3` | `True` |
| `<` | menor que | `5 < 3` | `False` |
| `>=` | maior ou igual | `5 >= 5` | `True` |
| `<=` | menor ou igual | `4 <= 3` | `False` |

```python
saldo = 200
limite = 500
dentro_do_limite = saldo <= limite
print(dentro_do_limite)  # True
```

⚠️ Erro comum: usar `=` (atribuição) quando o objetivo é `==` (comparação).
`=` guarda um valor; `==` compara dois valores.

### Operadores lógicos

Combinam duas ou mais expressões lógicas (valores `bool`).

| Operador | Significado | Exemplo | Resultado |
|---|---|---|---|
| `and` | verdadeiro só se **ambos** forem verdadeiros | `True and False` | `False` |
| `or` | verdadeiro se **pelo menos um** for verdadeiro | `True or False` | `True` |
| `not` | inverte o valor lógico | `not True` | `False` |

```python
idade = 20
tem_documento = True
pode_votar = idade >= 16 and tem_documento
print(pode_votar)  # True
```

---

## 5. Variáveis string

Uma `string` (`str`) representa texto, delimitado por aspas simples `'...'`
ou duplas `"..."` — as duas formas funcionam igual em Python.

```python
cidade = "São Paulo"
sigla = 'SP'
```

Strings são **imutáveis**: uma vez criadas, não é possível alterar um
caractere específico dentro delas. Para "mudar" uma string, cria-se uma
nova.

### Função `len()`

Retorna o número de caracteres da string (incluindo espaços).

```python
nome = "Maria Clara"
print(len(nome))  # 11
```

### Índice (posição)

Cada caractere de uma string tem uma posição numerada, começando em `0`
(não em `1`).

```python
palavra = "PYTHON"
#           P  Y  T  H  O  N
# índice:   0  1  2  3  4  5
# índice negativo: -6 -5 -4 -3 -2 -1

print(palavra[0])   # 'P'  (primeiro caractere)
print(palavra[-1])  # 'N'  (último caractere)
```

Índices negativos contam a partir do final da string, o que é útil para
pegar o último caractere sem precisar saber o tamanho exato da string.

### Operações com string

#### Concatenação

Juntar strings usando `+`:

```python
nome = "Ana"
sobrenome = "Silva"
nome_completo = nome + " " + sobrenome
print(nome_completo)  # 'Ana Silva'
```

#### Composição (f-strings)

Forma recomendada de combinar texto com variáveis, usando `f"..."`:

```python
produto = "notebook"
preco = 3500
mensagem = f"O produto {produto} custa R$ {preco}"
print(mensagem)  # 'O produto notebook custa R$ 3500'
```

A f-string é preferível à concatenação com `+` porque é mais legível e
converte números automaticamente para texto.

#### Fatiamento de string (slicing)

Permite extrair um pedaço (substring) usando `string[inicio:fim:passo]`.
O caractere na posição `fim` **não é incluído**.

```python
palavra = "PYTHON"

print(palavra[0:3])   # 'PYT'  (posições 0, 1, 2)
print(palavra[2:])    # 'THON' (do índice 2 até o final)
print(palavra[:3])    # 'PYT'  (do início até o índice 2)
print(palavra[::-1])  # 'NOHTYP' (passo -1 = inverte a string)
```

| Fatia | Significado |
|---|---|
| `s[a:b]` | do índice `a` até `b-1` |
| `s[:b]` | do início até `b-1` |
| `s[a:]` | do índice `a` até o final |
| `s[::-1]` | string invertida |

---

## 6. Sequência de execução e rastreamento

Python executa o código **linha por linha, de cima para baixo**. O valor de
uma variável é sempre o **último valor atribuído a ela**, não o primeiro.

```python
contador = 0
contador = contador + 1
contador = contador + 1
print(contador)  # 2
```

"Rastrear" o código (trace) é o exercício de acompanhar, linha por linha, o
que cada variável vale naquele momento. É uma técnica essencial para
encontrar erros de lógica.

| Linha | Código | `contador` depois |
|---|---|---|
| 1 | `contador = 0` | `0` |
| 2 | `contador = contador + 1` | `1` |
| 3 | `contador = contador + 1` | `2` |

Antes de rodar um código para conferir o resultado, tente montar essa
tabela mentalmente (ou no papel) — é assim que se debuga código sem
depender só do computador.

---

## 7. Entrada de dados

A função `input()` recebe um dado digitado pelo usuário no terminal.

```python
nome = input("Digite seu nome: ")
print(f"Olá, {nome}!")
```

⚠️ Ponto essencial: **`input()` sempre retorna uma `string`**, mesmo que a
pessoa digite números.

```python
idade = input("Digite sua idade: ")
print(type(idade))  # <class 'str'>  (mesmo digitando "25")
```

### Conversão da entrada de dados

Para usar o valor digitado como número, é preciso converter explicitamente:

```python
idade = input("Digite sua idade: ")
idade = int(idade)          # converte string para int
print(idade + 1)            # agora funciona como número
```

| Função | Converte para |
|---|---|
| `int()` | número inteiro |
| `float()` | número decimal |
| `str()` | texto |

### Erros comuns

- **Esquecer de converter**: tentar somar `"25" + 1` gera `TypeError`,
  porque não dá para somar `str` com `int` diretamente.
- **Converter texto que não é número**: `int("vinte e cinco")` gera
  `ValueError`, porque `"vinte e cinco"` não representa um número válido.
- **Espaços extras**: `int(" 25 ")` na verdade funciona (Python ignora
  espaços nas pontas), mas `int("25 anos")` gera erro.
- **Confundir `int()` com `float()`**: `int("3.5")` gera `ValueError` —
  para converter texto com casas decimais, use `float()` primeiro.

Esses erros geram uma mensagem de `Traceback` no terminal. Por enquanto,
basta reconhecer a causa; o tratamento desses erros com `try/except` é
assunto do Módulo 03.

---

## Resumo rápido

| Conceito | Como fazer |
|---|---|
| Criar variável | `nome = valor` |
| Ver o tipo | `type(variavel)` |
| Comparar valores | `==`, `!=`, `>`, `<`, `>=`, `<=` |
| Combinar condições | `and`, `or`, `not` |
| Tamanho de string | `len(texto)` |
| Acessar caractere | `texto[indice]` |
| Fatiar string | `texto[inicio:fim:passo]` |
| Ler entrada do usuário | `input("mensagem: ")` |
| Converter tipo | `int()`, `float()`, `str()` |

Próximo arquivo → `01_variaveis_tipos.ipynb` para praticar cada tópico.
