# 🐍 Introdução ao Python

> **Python-study** · Trilha Python para Dados · Módulo 01

Leia este arquivo antes de abrir qualquer exercício.
Aqui você vai entender **como Python pensa**, não só como escrever código, mas por que ele funciona do jeito que funciona.

---

## O que é Python?

Python é uma linguagem de programação criada em 1991 por Guido van Rossum. É uma das linguagens mais usadas no mundo, especialmente em ciência de dados, engenharia de dados e inteligência artificial.

Por que Python é tão popular para dados?

- Sintaxe simples e próxima do inglês
- Enorme ecossistema de bibliotecas (pandas, numpy, matplotlib)
- Comunidade ativa e muita documentação
- Roda em qualquer sistema operacional

---

## Como Python executa seu código

Python lê e executa seu código **linha por linha, de cima para baixo**.

```python
print("Linha 1")   # executa primeiro
print("Linha 2")   # executa depois
print("Linha 3")   # executa por último
```

Isso parece óbvio agora, mas vai fazer diferença quando você aprender loops e funções.

---

## Comentários

Comentários são linhas que Python **ignora completamente**. Servem para você explicar o que o código faz, para você mesma no futuro, ou para quem vai ler seu código.

Todo comentário começa com `#`:

```python
# Isso é um comentário, Python ignora esta linha
print("Olá")  # comentário no final de uma linha de código

# Você pode usar comentários para:
# - Explicar o que uma variável armazena
# - Descrever o que uma função faz
# - Deixar lembretes para si mesma
```

> 💡 **Bom hábito:** escreva comentários em português claro. Código bem comentado é código profissional.

---

## Indentação

Indentação é o espaço no início de uma linha. Em Python, a indentação **não é opcional**, ela define a estrutura do código.

Em outras linguagens, chaves `{}` delimitam blocos de código. Em Python, é a indentação:

```python
# Correto - indentação com 4 espaços
if True:
    print("Dentro do bloco")   # 4 espaços
    print("Ainda dentro")      # 4 espaços
print("Fora do bloco")         # sem espaço

# Errado - vai gerar IndentationError
if True:
print("Sem indentação")  # ❌ erro!
```

**Regra:** use sempre **4 espaços** para indentar. O VS Code faz isso automaticamente quando você pressiona Tab.

> ⚠️ **Cuidado:** misturar espaços e tabs causa erros difíceis de encontrar. Configure seu editor para usar sempre espaços.

---

## Tudo é objeto

Esta é uma das ideias mais importantes do Python:

**Em Python, tudo é um objeto.**

Números, textos, listas, funções - tudo. E cada objeto tem:
- Um **tipo** (o que ele é)
- Um **valor** (o que ele armazena)
- **Métodos** (o que ele sabe fazer)

```python
# O número 42 é um objeto do tipo int
numero = 42
print(type(numero))   # <class 'int'>

# O texto "dados" é um objeto do tipo str
texto = "dados"
print(type(texto))    # <class 'str'>

# True é um objeto do tipo bool
ativo = True
print(type(ativo))    # <class 'bool'>
```

Por que isso importa? Porque quando você entende que tudo é objeto, você entende por que pode "chamar coisas" em cima de variáveis - como `texto.upper()` ou `texto.replace()`. Esses são os **métodos** do objeto.

---

## Variáveis

Uma variável é um **nome que aponta para um valor** na memória do computador.

```python
nome = "Ana"      # a variável 'nome' aponta para o texto "Ana"
idade = 25        # a variável 'idade' aponta para o número 25
altura = 1.65     # a variável 'altura' aponta para o decimal 1.65
```

### Como nomear variáveis

| ✅ Correto | ❌ Errado | Motivo |
|---|---|---|
| `nome_completo` | `nome completo` | sem espaços |
| `idade` | `1idade` | não começa com número |
| `valor_total` | `valor-total` | hífen não é permitido |
| `ativo` | `True` | True é palavra reservada |
| `preco` | `preço` | evite acentos |

### Convenção de nomes em Python

Python usa **snake_case** - palavras em minúsculo separadas por underscore:

```python
# snake_case — padrão Python
nome_completo = "Ana Silva"
valor_total = 1500.0
esta_ativo = True

# NÃO use camelCase para variáveis (é padrão de outras linguagens)
nomeCompleto = "Ana Silva"  # evite em Python
```

### Variáveis são dinâmicas

Em Python, você pode reatribuir uma variável com um tipo diferente:

```python
x = 10        # x é int
x = "dados"   # agora x é str — Python aceita isso
x = True      # agora x é bool
```

> 💡 Isso é diferente de linguagens como Java ou C, onde você precisa declarar o tipo da variável.

---

## Tipos de dados

Python tem quatro tipos básicos que você vai usar o tempo todo:

### int - número inteiro
```python
idade = 25
quantidade = 1000
ano = 2024
```

### float - número decimal
```python
altura = 1.65
preco = 49.90
taxa = 0.05
```

### str - texto (string)
```python
nome = "Ana"
cidade = 'São Paulo'   # aspas simples ou duplas — tanto faz
frase = "Python para dados"
```

### bool - verdadeiro ou falso
```python
ativo = True
inativo = False
maior_de_idade = True
```

---

## Funções

Uma função é um **bloco de código com um nome**, que você pode chamar quantas vezes quiser.

Python já vem com várias funções prontas - chamadas de **funções built-in**:

```python
print("Olá")           # exibe texto na tela
type(42)               # retorna o tipo de um valor
len("Python")          # retorna o tamanho de uma string
int("42")              # converte para inteiro
float("3.14")          # converte para decimal
str(100)               # converte para texto
input("Digite algo: ") # lê o que o usuário digita
```

### Como uma função funciona

```
nome_da_funcao(argumento)
      ↑              ↑
  o que chamar   o que passar
```

```python
# Chamando a função print com o argumento "Olá"
print("Olá")

# Chamando a função len com a variável nome
nome = "Python"
tamanho = len(nome)
print(tamanho)  # 6
```

---

## Métodos

Métodos são funções que **pertencem a um objeto**. A diferença é que você chama o método usando um ponto `.` depois do objeto:

```python
# Sintaxe: objeto.metodo()
texto = "python para dados"

print(texto.upper())      # PYTHON PARA DADOS
print(texto.capitalize()) # Python para dados
print(texto.replace("python", "Python"))  # Python para dados
print(texto.split())      # ['python', 'para', 'dados']
```

A diferença entre função e método:

```python
# Função - você passa o objeto como argumento
len(texto)      # função built-in

# Método - você chama a partir do objeto
texto.upper()   # método do objeto str
```

> 💡 **Como lembrar:** método é uma função que "pertence" a um tipo específico de objeto. `upper()` só existe em strings — você não pode chamar `42.upper()`.

---

## Classes

Uma classe é o **molde** que define como um tipo de objeto funciona.

Você ainda não vai criar suas próprias classes agora, mas é importante entender o conceito porque Python usa classes para tudo:

```python
# Quando você faz isso:
texto = "dados"

# Python cria internamente um objeto da classe str
# A classe str define:
# - que o objeto armazena texto
# - quais métodos ele tem (upper, lower, replace, split...)
# - como ele se comporta com operadores (+ para concatenar, etc.)

print(type(texto))  # <class 'str'>
#                          ↑
#                    isso é o nome da classe
```

Pense assim:
- **Classe** = receita de bolo (define como fazer)
- **Objeto** = o bolo pronto (criado a partir da receita)
- **Método** = o que você pode fazer com o bolo (fatiar, decorar...)

---

## Operadores

### Operadores aritméticos
```python
10 + 3   # 13  — soma
10 - 3   # 7   — subtração
10 * 3   # 30  — multiplicação
10 / 3   # 3.333... — divisão (sempre retorna float)
10 // 3  # 3   — divisão inteira (descarta o decimal)
10 % 3   # 1   — resto da divisão (módulo)
2 ** 10  # 1024 — potência
```

### Operadores relacionais
Comparam dois valores e retornam `True` ou `False`:

```python
10 > 5    # True  — maior que
10 < 5    # False — menor que
10 >= 10  # True  — maior ou igual
10 <= 9   # False — menor ou igual
10 == 10  # True  — igual (dois sinais de igual!)
10 != 5   # True  — diferente
```

> ⚠️ **Cuidado:** `=` é atribuição (guarda um valor). `==` é comparação (verifica se são iguais). Confundir os dois é um erro muito comum no início.

### Operadores lógicos
Combinam condições booleanas:

```python
True and True    # True  — ambos precisam ser True
True and False   # False
True or False    # True  — pelo menos um precisa ser True
False or False   # False
not True         # False — inverte o valor
not False        # True
```

Exemplo prático:
```python
idade = 25
tem_conta = True

pode_acessar = idade >= 18 and tem_conta
print(pode_acessar)  # True
```

---

## Operações com String

Strings são objetos ricos em Python. Você pode fazer muito com elas.

### Concatenação — juntar strings
```python
primeiro = "Ana"
ultimo = "Silva"
nome_completo = primeiro + " " + ultimo
print(nome_completo)  # Ana Silva
```

### Composição - f-string (forma moderna)
```python
nome = "Ana"
idade = 25
print(f"Olá, {nome}! Você tem {idade} anos.")
# Olá, Ana! Você tem 25 anos.

# Você pode fazer cálculos dentro das chaves
preco = 49.90
quantidade = 3
print(f"Total: R$ {preco * quantidade:.2f}")
# Total: R$ 149.70
```

### Len - tamanho da string
```python
texto = "Python"
print(len(texto))  # 6
```

### Métodos essenciais de string
```python
texto = "  Python para Dados  "

texto.strip()           # "Python para Dados"  — remove espaços
texto.upper()           # "  PYTHON PARA DADOS  "
texto.lower()           # "  python para dados  "
texto.replace("a", "A") # "  Python pArA DAdos  "
texto.split()           # ["Python", "para", "Dados"]
texto.startswith("  P") # True
texto.endswith("s  ")   # True
" ".join(["a", "b"])    # "a b"
```

### Slice - fatiamento
Slice permite extrair partes de uma string usando índices:

```python
texto = "Python"
#        0 1 2 3 4 5   ← índices positivos
#       -6-5-4-3-2-1   ← índices negativos

texto[0]      # "P"   — primeiro caractere
texto[-1]     # "n"   — último caractere
texto[0:3]    # "Pyt" — do índice 0 até 2 (o 3 não entra)
texto[2:]     # "thon" — do índice 2 até o fim
texto[:4]     # "Pyth" — do início até o índice 3
texto[::2]    # "Pto" — um a cada dois
texto[::-1]   # "nohtyP" — invertido!
```

### Inversão de string
```python
texto = "Python"
invertido = texto[::-1]
print(invertido)  # nohtyP
```

---

## Entrada de dados

A função `input()` pausa o programa e espera o usuário digitar algo. Sempre retorna uma **string**, independente do que foi digitado:

```python
nome = input("Digite seu nome: ")
print(f"Olá, {nome}!")
```

### Conversão na entrada de dados

Como `input()` sempre retorna string, você precisa converter quando quiser um número:

```python
# Sem conversão — erro!
idade = input("Sua idade: ")
proximo_aniversario = idade + 1  # ❌ TypeError: não dá para somar str com int

# Com conversão — correto
idade = int(input("Sua idade: "))
proximo_aniversario = idade + 1  # ✅ funciona
print(f"No próximo aniversário você terá {proximo_aniversario} anos.")

# Para número decimal
altura = float(input("Sua altura: "))
```

> 💡 **Padrão:** sempre converta o `input()` na mesma linha. Fica mais limpo e evita erros.

---

## Rastreamento - como ler um erro

Quando seu código tem um erro, Python mostra um **traceback** (rastreamento). Não entre em pânico — leia de baixo para cima:

```
Traceback (most recent call last):
  File "exemplo.py", line 3, in <module>
    resultado = "10" + 5
TypeError: can only concatenate str (not "int") to str
           ↑
     leia esta linha primeiro — ela diz o que deu errado
```

Os erros mais comuns no início:

| Erro | O que significa |
|---|---|
| `SyntaxError` | Erro de escrita — faltou `:`, `)`, aspas, etc. |
| `IndentationError` | Indentação errada |
| `TypeError` | Tipo errado - tentou somar str com int, por exemplo |
| `NameError` | Variável usada antes de ser criada |
| `ValueError` | Valor inválido - ex: `int("abc")` |

---

## Resumo

| Conceito | O que é | Exemplo |
|---|---|---|
| Comentário | Linha ignorada pelo Python | `# isso é um comentário` |
| Indentação | Espaços que definem blocos | `    print("dentro")` |
| Variável | Nome que aponta para um valor | `nome = "Ana"` |
| Tipo | O que o objeto é | `int`, `float`, `str`, `bool` |
| Função | Bloco de código com nome | `print()`, `len()`, `type()` |
| Método | Função de um objeto | `texto.upper()` |
| Classe | Molde que define um tipo | `str`, `int`, `list` |
| Slice | Fatiar uma sequência | `texto[0:3]` |
| f-string | Compor texto com variáveis | `f"Olá, {nome}"` |

---

## Próximo passo

Agora que você entende como Python pensa, abra o notebook:

→ [`01_variaveis_tipos.ipynb`](./01_variaveis_tipos.ipynb)

---

<div align="center">

💜 [Python-study](https://github.com/Python-plancton) · open source · feito para profissionais de dados inciantes

</div>
