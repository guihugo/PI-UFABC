# PI - Semana 1

Introdução e conceitos básicos de processamento da informação através da linguagem Python:

- Variáveis
- Tipos de dados
- Entrada e saída
- Operadores
- Funções

---

## Python 3

### Site oficial: [www.python.org](https://www.python.org)

### Documentação oficial em português: [https://docs.python.org/pt-br/3/](https://docs.python.org/pt-br/3/)

---

## Interpretador Python

O interpretador Python é o programa que lê e executa comandos da linguagem Python. 

### Ambiente REPL

O interpretador Python pode ser executado no chamado "ambiente REPL" (_Read-Eval-Print-Loop_). Esse é um modo interativo no qual os comandos digitados em uma linha são executados imediatamente após a tecla <kbd>Enter</kbd> ser pressionada. O ambiente REPL é útil para testar rapidamente comandos e expressões do Python.

Para abrir o interpretador como um ambiente REPL, abra um terminal de linha de comando (`cmd.exe` no Windows, ou shell do Linux/macOS) e digite `python` seguido de <kbd>Enter</kbd>:

```
python
```

> **Observação**
>
> Se `python` não for encontrado, tente `python3` ou `python3.10` (se a versão instalada é a 3.10).

O ambiente REPL exibe um _prompt_ de comando (`>>>`) esperando que algo seja digitado:

```
Python 3.10.6 (main, Mar 10 2023, 10:55:28) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 
```

Você pode agora digitar um comando ou expressão em Python. O comando/expressão será executado imediatamente assim que <kbd>Enter</kbd> for pressionado. Por exemplo, digite `2+2` e <kbd>Enter</kbd>:

```
>>> 2+2
4
```

Digite `print("Olá, mundo!")`:

```
>>> print("Olá, mundo!")
Olá, mundo!
```

O comando `print` imprime na tela os caracteres (letras, números e símbolos) que estão entre aspas.

Para sair do ambiente REPL, digite `quit()` ou pressione <kbd>Ctrl+d</kbd> (no Linux/macOS) ou <kbd>Ctrl+z</kbd> seguido de <kbd>Enter</kbd> (no Windows).

## Interpretando programas

O interpretador Python pode ser usado para interpretar uma sequência de comandos em Python. Essa sequência de comandos constitui um _programa_ em Python.

Os comandos devem ser digitados dentro de um arquivo em formato de texto não formatado. Esse arquivo de comandos é comumente chamado de "código fonte" do programa.

Eis o código fonte de um programa que imprime "Olá," em uma linha e "mundo!" em outra linha.:

```python
print("Olá,")
print("mundo!")
```

Use um editor de texto não formatado (ex: Bloco de Notas) para digitar o programa acima. Em seguida, salve-o com a extensão ".py". Por exemplo, `olamundo.py`. No terminal, execute `python`, mas passe `olamundo.py` como um argumento, assim:

```
python olamundo.py
```

Internamente, o interpretador Python lerá `olamundo.py` e então _interpretará_ cada linha do código fonte, como se cada linha de `olamundo.py` fosse digitada no ambiente REPL, seguida de <kbd>Enter</kbd>. A saída da tela será

```
Olá,
mundo!
```

Se você quiser rodar seu programa em outro computador, você deverá copiar seu arquivo `olamundo.py` e executar `python olamundo.py` neste outro computador. Entretanto, isso só funcionará se esse outro computador tiver o interpretador Python instalado.

Em outras linguagens de programação como [C](https://pt.wikipedia.org/wiki/C_(linguagem_de_programa%C3%A7%C3%A3o)), [C++](https://pt.wikipedia.org/wiki/C%2B%2B) e [Rust](https://pt.wikipedia.org/wiki/Rust_(linguagem_de_programa%C3%A7%C3%A3o)), o código fonte é primeiro processado por um programa chamado _compilador_. O compilador gera um novo arquivo que pode ser um arquivo executável. A vantagem do arquivo compilado é que ele não depende mais do código fonte e não precisa de um interpretador para funcionar. Por outro lado, a desvantagem é que o processo de compilação é uma etapa a mais que o desenvolvedor precisa usar, e não serve como um ambiente REPL.

> **Observação**
>
> O arquivo gerado pelo compilador não é mais um arquivo em formato texto; é um arquivo _binário_ que contém sequências de bytes que definem instruções em _linguagem de máquina_. A linguagem de máquina é a linguagem utilizada pelo processador do computador, e portanto é muito rápida. Por outro lado, é uma linguagem de baixo nível de abstração que não foi feita para humanos utilizarem diretamente.

---

## Instalando Python no Visual Studio Code

Usaremos o [Visual Studio Code](https://code.visualstudio.com/) (VS Code) como editor de código fonte Python. O VS Code é mais conveniente que editores simples como o Bloco de Notas pois fornece facilidades para a edição, execução, teste e depuração de programas em Python.

Após instalar o VS Code, instale as seguintes extensões:

- [Python](https://marketplace.visualstudio.com/items?itemName=ms-python.python): extensão principal que instala outras extensões de produtividade de desenvolvimento em Python.
- [PyLint](https://marketplace.visualstudio.com/items?itemName=ms-python.pylint): extensão para usar o _linter_ `pylint`. Um _linter_ é uma ferramenta de análise de código que detecta erros de programação, bugs e erros de estilo.
- [Black Formatter](https://marketplace.visualstudio.com/items?itemName=ms-python.black-formatter): permite formatar o código fonte automaticamente. Após instalar esta extensão, adicione as seguintes linhas de configuração no arquivo de configurações do usuário do VS Code. Isso serve para que a formatação seja feita automaticamente sempre que o arquivo for salvo:

  ```json
  "[python]": {
    "editor.defaultFormatter": "ms-python.black-formatter",
    "editor.formatOnSave": true
  }
  ```

  Para abrir o arquivo de configurações do usuário, pressione <kbd>Ctrl+Shift+P</kbd> (paleta de comandos), e então escreva "Preferences: Open User Settings (JSON)".

> **Observação**
>
> Em alguns casos pode ser conveniente desabilitar a análise de código do PyLint para um código fonte específico. Para isso, basta incluir o seguinte texto na primeira linha do arquivo:
>     
>```python
># pylint: disable=all
>```
> ***

## Variáveis e Tipos de Dados

Uma variável identifica, através de um **nome**, um endereço da memória que contém um **dado** de algum **tipo**.

Um dado (valor) pode ser atribuído a uma variável através do **operador de atribuição** (`=`), como na declaração abaixo:

```python
ano = 2023
```

Nesta linha, estamos criando (_declarando_) uma variável chamada `ano` e _definindo_ seu valor para `2023`. 

O interpretador Python reconhece automaticamente que o tipo de dado neste caso é um `int` (número inteiro) pois `2023` é um número inteiro.

Quando Python interpreta essa linha, o computador reserva automaticamente um espaço na memória para guardar o valor `2023`.

O nome `ano` passa a ser um "apelido" (em inglês, _alias_) ao endereço de memória que contém o valor `2023`. O interpretador Python determina automaticamente quantos bytes são necessários para representar esse valor.

Outros exemplos de declaração de variáveis:

```python
idade = 21
pi = 3.141592
nome = "Luís Paulo"
```
Uma característica da linguagem Python é que é possível declarar diferentes variáveis em uma mesma linha. Para isso, basta separar os nomes e valores por vírgula. Por exemplo, as variáveis do exemplo anterior podem ser criadas em uma mesma linha da seguinte forma:

```python
idade, pi, nome = 21, 3.141592, "Luís Paulo"
```

Uma vez que uma variável foi declarada (isto é, criada), podemos mudar seu valor. Para isso basta usar novamente o operador de atribuição:

```python
x = 10  # Cria a variável x
x = 15  # Modifica a variável x já existente
```

Podemos também mudar o tipo de dado da variável já existente:

```python
y = 10    # Cria a variável y do tipo int
y = "abc" # Modifica a variável y, que agora passa a ser do tipo str (texto ou string)
```

### Comentários

Observe, nos exemplos anteriores, que usamos o caractere cerquilha `#` para inserir comentários dentro do código. O comentário começa depois de `#` e se estende até o final da linha: 

```python
ano = 2023 # Lembrete: no ano que vem preciso atualizar para 2024
```

Comentários são ignorados pelo interpretador Python, mas servem como uma forma de documentação do código. A documentação através de comentários é útil para esclarecer o código para outros programadores e para nós mesmos no futuro.

Uma outra forma de inserir comentários é através do uso de texto delimitado por três aspas duplas `"""`. Em Python, esse tipo de texto é chamado de _docstring_:

```python
"""Isso é um docstring"""
x = 10
```
Com docstrings podemos estender um comentário em múltiplas linhas, como a seguir:

```python
"""
Olá!

Este é um programa bem simples que cria uma variável x que contém o valor 10.

Este programa também demonstra o uso de docstring para inserir múltiplas linhas 
de comentário.

Na verdade, um docstring não é exatamente um comentário; é apenas uma cadeia 
literal de caracteres que não está sendo atribuída a nenhuma variável, e por 
isso acaba sendo ignorada pelo interpretador.
"""
x = 10
```

### Nomenclatura

Em Python, nomes de variáveis só podem conter letras, números e o caractere de sublinhado `_` (_underscore_). O nome não pode começar com um número e não pode conter espaços.

```python
# CORRETO
ano_atual = 2023
idade4 = 50
valorDevido = 10.5
Nome_da_Disciplina = "Processamento da Informação"

# ERRADO
ano atual = 2023
4idade = 50
valor.devido = 10.5
Nome_d@_D1sciplina = "Processamento da Informação"
```

> ### **Exercício - Troca de variáveis**
>
> Considere o seguinte programa que define duas variáveis e imprime seu conteúdo na tela:
>
> ```python
> x = 42
> y = "PI-UFABC"
>
> # Insira seu código aqui
>
> print(x)
> print(y)
> ```
> Se esse programa for executado, será mostrado na tela `42` e `PI-UFABC`, nesta ordem.
>
> Substitua o comentário por um trecho de código que troca os valores de `x` e `y` (o que está em `x` deve ir para `y`, e vice-versa).
>
> Assim, quando o programa for executado, deve ser mostrado na tela `PI-UFABC` e `42`, nesta ordem.
>
> Atenção! não vale fazer o seguinte:
> ```python
> x = "PI-UFABC"
> y = 42
> ```
> ****

### Tipos de Dados

A seguir veremos alguns tipos básicos de dados em Python que são também tipos básicos em outras linguagens de programação:

## `int`
Número inteiro:

```python
x = 42  
y = -42
z = +42  # A mesma coisa que 42
```

## `float`
Número real em notação de _ponto flutuante_:

```python
x = 10.0  # Note o uso do ponto como separador decimal
y = 3.14
z = 2e-1  # Notação científica
w = -5E2  # Notação científica
```
> **Observação**
>
> Números em ponto flutuante possuem uma precisão finita, e por isso não são como os números reais de verdade. Por exemplo, experimente fazer `3.14159265e-20 * 1e20`. O resultado deveria ser `3.14159265`, mas não é pois a operação introduz erros de precisão numérica.

## `bool`
Valor lógico (verdadeiro ou falso):

```python
x = True
y = False
```

## `str`
Cadeira de caracteres, ou _string_: 

```python
letra_do_alfabeto = "a"
universidade = "UFABC"
universidade = 'UFABC'  # Funciona também com aspas simples
string_vazia = ""
```

Também podemos usar texto entre três aspas duplas `"""` para criar uma string que se estende por múltiplas linhas:

```python
multiplas_linhas = """Linha 1
linha 2
linha 3
"""
```

O tipo de dado determina quais operações podem ser feitas com o dado. Por exemplo, podemos fazer operações aritméticas com `int` e `float` (somar, subtrair, multiplicar, dividir, etc), operações lógicas com `bool` (_e_, _ou_ e _não_), e concatenação de texto com `str`.

### O comando `type()`

O comando `type()` serve para mostrar o tipo de dado de uma variável ou valor literal escrito entre os parênteses. Veja o seguinte exemplo no ambiente REPL:

```
>>> x=42
>>> type(x)
<class 'int'>
```
O tipo de dado de `x` é `int`.

> Mais precisamente, `x` é um _objeto da classe_ `int`. Os conceitos de _classe_ e _objeto_ são conceitos mais avançados de programação e são abordados na disciplina de "Programação Orientada a Objetos". Em Processamento da Informação não precisamos nos aprofundar nesses conceitos.

Veja a seguir outros exemplos do uso de `type()`, dessa vez usando valores literais e expressões ao invés de nomes de variáveis:

```
>>> type("Que tipo de dado é esse?")
<class 'str'>
>>> type(True)
<class 'bool'>
>>> type(5.2 + 4)
<class 'float'>
>>>
```

### Conversão entre tipos

Podemos usar os comandos `int()`, `float()`, `bool()` e `str()` para converter um tipo de dado em outro. 

Considere o seguinte exemplo:

```plain
x = "10"
y = "5"
```

Qual é resultado de `x+y`? Experimente no ambiente REPL:

```plain
>>> x="10"
>>> y="5"
>>> x+y
'105'
```

Por que o resultado não é `15`? Por causa do tipo de dado!

Observe as aspas na definição das variáveis: `x` e `y` são variáveis do tipo `str`.

Em Python, o uso do operador `+` sobre duas strings resulta na concatenação das strings. Logo, o resultado é uma nova string, `"105"`. 

> Lembre-se que todos os caracteres entre aspas simples ou duplas são considerados como valores do tipo `str`.

Para realizarmos a soma de `x` e `y` como números, primeiro precisamos converter `"10"` e `"5"` para `int`. Podemos fazer isso com o comando `int()`:

```plain
>>> x="10"
>>> y="5"
>>> int(x) + int(y)
15
```
A expressão `int(x) + int(y)` é interpretada de acordo com a seguinte sequência de passos:

1. Primeiro, os valores de `x` e `y` são obtidos. O resultado é uma nova expressão:
    ```python
    int("10") + int("5")
    ```
2. Em seguida, as funções `int` são avaliadas sobre tais valores. O resultado é uma nova expressão:
    ```python
    10 + 5
    ``` 
3. Por fim, a soma é realizada. O resultado é uma nova expressão:
    ```python
    15
    ```
4. Como o `15` não está sendo atribuído a nenhuma variável, ele é simplesmente mostrado na tela, como se o usuário digitasse `15` e presionasse <kbd>Enter</kbd> (fora do ambiente REPL não é mostrado nada).

`int(x)` só funciona se os caracteres da string `x` forem dígitos de 0 a 9, opcionalmente com um sinal de mais (`+`) ou de menos (`-`) imediatamente antes do primeiro dígito:

```python
int("10")     # 10
int(" 010  ") # 10
int("+10")    # 10
int("-10")    # -10
int("10.0")   # ERRO
int("Dez")    # ERRO
int("2+2")    # ERRO
```

Também podemos usar `float` para converter strings em números em ponto flutuante:

```python
float("10")      # 10.0
float("3.1415")  # 3.1415
float("-2e3")    # -2000.0
float("2,5")     # ERRO: o separador decimal precisa ser ponto
```

Também é possível converter `float` e `bool` em `int`:

```python
int(10.0)   # 10
int(1E1)    # 10
int(2.5)    # 2 (a parte fracionária é descartada)
int(False)  # 0
int(True)   # 1
```

Na conversão de `int`, `float` e `str` para `bool` (e vice-versa):

* `0`, `0.0` e `""` (string vazia) resultam em `False`;
* Quaisquer outros valores resultam em `True`.
* `False` é convertido para `0`, `0.0` e `""` (string vazia).
* `True` é convertido para `1`, `1.0` e `"1"`.

---

## Entrada e Saída de Dados

Para a entrada de dados a partir do teclado, podemos usar o comando `input(str)`, onde `str` é uma string opcional que é mostrada na tela antes do cursor de entrada do teclado.

Para a saída de dados na tela, podemos usar `print(x)`, onde `x` é qualquer variável ou expressão que possa ser convertida em um dado do tipo `str`:

```python
nome = input("Digite o seu nome: ")
print("Olá, " + nome + ". Tudo bem?")
```

Neste exemplo, a mensagem `Digite o seu nome:` é exibida na tela e o cursor do teclado fica piscando esperando o usuário digitar algo.

Assim que o usuário digitar algo e pressionar <kbd>Enter</kbd>, o texto digitado será atribuído à variável `nome`.

Em seguida, a string `"Olá, "` é concatenada com a string contida na variável `nome`, e então é concatenada com a string `". Tudo bem?"`. Por fim, o resultado é mostrado na tela pelo `print()`.

Uma outra forma de usar o `print()` é assim:

```python
print("Olá, {}. Tudo bem?".format(nome))
```
As chaves `{}` são substituídas pelo conteúdo de `nome`. Essa é uma forma alternativa ao uso de concatenação de strings. Também é possível colocar mais chaves e variáveis, como no exemplo a seguir:


```python
nome = "Luís Paulo"
ano = 2023
print("Olá, {}. Sabia que estamos no ano de {}?".format(nome, ano))
```

O resultado na tela será:

```
Olá, Luís Paulo. Sabia que estamos no ano de 2023?
```

Veja que cada grupo de chaves foi substituído, em ordem, pelo conteúdo de cada variável informada no `format()`.

Há ainda outra forma de usar `print()`: com o uso de _strings formatadas_ ou _f-strings_, assim:

```python
print(f"Olá, {nome}. Tudo bem?")
```

Observe o `f` antes do início da string para indicar que é uma f-string. Dentro da f-string, o que estiver entre chaves será substituído pelo conteúdo da variável correspondente.

Tanto no uso de `format()` quanto no uso de f-strings, se a expressão entre chaves for avaliada como um número, é possível informar o número de casas decimais que serão mostradas na tela. Por exemplo:

```
>>> x=1/3
>>> x
0.3333333333333333
>>> print(f"{x}")
0.3333333333333333
>>> print(f"{x:.2f}")
0.33
```

No exemplo acima, `{x}` imprime o número padrão de casas decimais, enquanto que `{x:.2f}` informa que `x` deve ser mostrado com apenas duas casas decimais. Se quisermos mostrar três casas decimais, usaremos `{x:.3f}`, e assim por diante.

> ### **Exercício - Saudação**
>
> Faça um programa que pede para o usuário seu nome, sobrenome, e então mostra na tela uma mensagem de saudação, seguida da mensagem "Gostei do seu nome.".
>
> Veja um exemplo de execução do programa:
>
> ```
> Digite seu nome: Harlen
> Digite seu sobrenome: Batagelo
> Bom dia, Harlen Batagelo!
> Gostei do seu nome.
> ```
> ***

---

## Operadores básicos

### Operadores aritméticos

Compreendem as operações básicas da aritmética.

Operador | Descrição                | Exemplo         
:------- | :----------------------- | :---------------
`+`      | soma                     | `2 + 2`
`-`      | subtração                | `10 - y`
`*`      | multiplicação            | `x * 2`
`/`      | divisão                  | `5 / 2` (resultado é `2.5`)
`//`     | divisão inteira          | `5 // 2` (resultado é `2`)
`%`      | resto da divisão inteira | `5 % 3` (resultado é `2`)
`**`     | exponenciação            | `2**3` (resultado é `8`)

Como vimos anteriormente, `+` também é usado para concatenação entre strings.

`*` pode ser usado para repetir a string um número de vezes determinado por um `int`:

Exemplo de concatenação e repetição:
```
>>> "UF" + "ABC"
'UFABC'
>>> "blá" * 3
'blábláblá'
```

Dica: podemos usar o operador de exponenciação `**` para calcular a raiz quadrada. Afinal, a raiz quadrada de um número é esse mesmo número elevado a 1/2. Veja alguns exemplos no REPL:

```
>>> 9**0.5
3.0
>>> 2**0.5
1.4142135623730951
>>> 36**(1/2)
6.0
```

Além dos operadores aritméticos, também estão disponíveis as seguintes funções embutidas:

* `abs(x)`: retorna o valor absoluto de `x`.
* `pow(b, e)`: retorna `b**e`.
* `bin(x)`: converte o inteiro `x` para binário, em uma string prefixada com `0b`.
* `hex(x)`: converte o inteiro `x` para hexadecimal, em uma string prefixada com `0x`.
* `oct(x)`: converte o inteiro `x` para octal, em uma string prefixada com `0o`.
* `min(arg1, arg2, ...)`: retorna o menor valor entre `arg1`, `arg2` e outros argumentos, se houverem.
* `max(arg1, arg2, ...)`: retorna o maior valor entre `arg1`, `arg2` e outros argumentos, se houverem.

### Operadores relacionais

Operadores relacionais são utilizados para fazer comparações entre dados. O resultado de uma expressão envolvendo um operador relacional é sempre um valor do tipo `bool`, isto é,  é `True` ou `False`.

Operador | Descrição                | Exemplo         
:------- | :----------------------- | :---------------
`<`      | menor que                | `x < 2`
`<=`     | menor ou igual a         | `x <= y`
`>`      | maior que                | `2.5 > 2`
`>=`     | maior ou igual a         | `z >= x`
`!=`     | diferente de             | `x != y`
`==`     | igualdade                | `x == y`

Usaremos operadores relacionais futuramente para criar estruturas de decisão.

> **Observação**
>
> Lembre-se que `x=y` é diferente de `x==y`.
> * `x=y` é uma atribuição e significa "coloque o valor de `y` em `x`";
> * `x==y` é uma comparação e significa "`x` é igual a `y`?".

### Operadores lógicos

Operadores lógicos são utilizados com dados do tipo `bool` ou dados que podem ser convertidos para `bool` seguindo as regras de conversão vistas anteriormente. 

Operadores lógicos são comumente utilizados para combinar expressões relacionais.

Operador | Descrição                | Exemplo         
:------- | :----------------------- | :---------------
`and`    | <kbd>E</kbd> lógico (conjunção)     | `(a >= 0) and (a < 10)`
`or`     | <kbd>OU</kbd> lógico (disjunção)    | `(media < 5) or (faltas > 6)`
`not`    | <kbd>NÃO</kbd> lógico (negação)     | `not game_over`
 
* A expressão `x and y` avalia primeiro o `x`.

  Se `x` é `False`, o resultado da expressão é `x`; senão, o resultado é `y`.
* A expressão `x or y` avalia primeiro o `x`.

  Se `x` is `True`, o resultado da expressão é `x`; senão, o resultado é `y`.
* Em `not x`, o operador `not` inverte o valor de `x`.

  Se `x` é `True`, `not x` é `False`. Se `x` é `False`, `not x` é `True`.

Usaremos operadores lógicas para criar estruturas de decisão em aulas futuras.

### Operadores de atribuição

Além do operador de atribuição `=`, existem outros que servem de atalho para combinar operações aritméticas com a operação de atribuição.

Operador | Descrição                                      | Exemplo         
:------- | :--------------------------------------------- | :---------------
`+=`     | adição seguida de atribuição                   | `x += 2` equivale a `x = x + 2`
`-=`     | subtração seguida de atribuição                | `x -= 2` equivale a `x = x - 2`
`*=`     | multiplicação seguida de atribuição            | `x *= 2` equivale a `x = x * 2`
`/=`     | divisão seguida de atribuição                  | `x /= 2` equivale a `x = x / 2`
`//=`    | divisão inteira seguida de atribuição          | `x //= 2` equivale a `x = x // 2`
`%=`     | resto da divisão inteiro seguida de atribuição | `x %= 2` equivale a `x = x % 2`
`**=`    | exponenciação seguida de atribuição            | `x **= 2` equivale a `x = x ** 2`

### Precedência dos operadores

Qual é o valor de `z` na expressão abaixo?

```python
x = 3
y = 2
z = - x ** 2 + 1 % y
```

Sabemos, das regras da matemática, que a ordem das operações segue o acrônimo `PEMDAS`:
1. `P`: parênteses;
2. `E`: exponenciação;
3. `MD`: multiplicação e divisão (da esquerda para a direita);
4. `AS`: adição e subtração (da esquerda para a direita).

Entretanto, na expressão acima temos o operador de resto da divisão `%` e o operador de inversão de sinal de `x`. Em qual ordem esses operadores devem ser aplicados?

Felizmente, a ordem dos operadores nas linguagens de programação é bem definida. Em Python, a ordem é a seguinte:

Ordem | Operador            | Descrição
:---- | :------------------ | :---------------
1     | `()`                | parênteses
2     | `**`                | exponenciação
3     | `+x`, `-x`          | positivo, negativo
4     | `*`, `/`, `//`, `%` | multiplicação, divisão, divisão inteira, resto da divisão inteira
5     | `+`, `-`            | adição, subtração
7     | `<`, `<=`, `>`, `>=`, `!=`, `==` | operadores relacionais
8     | `not x`             | <kbd>NÃO</kbd> lógico
9     | `and`               | <kbd>E</kbd> lógico
10    | `or`                | <kbd>OU</kbd> lógico
11    | `=`                 | atribuição

Os operadores que possuem a mesma ordem são avaliados da esquerda para a direita. Uma exceção é a exponenciação, que é avaliada da direita para a esquerda (por exemplo, `2 ** 2 ** 3` é `256`).

Usando a tabela de precedência, podemos determinar a ordem em que a expressão anterior é avaliada pelo interpretador Python. Para ficar mais claro, vamos enfatizar a operação avaliada em cada passo através de parênteses:

```python
z = - x ** 2 + 1 % y
z = - (x ** 2) + 1 % y  # Passo 1: x ** 2 (exponenciação)
z = (- 9) + 1 % y       # Passo 2: -9     (mudança do sinal)
z = -9 + (1 % y)        # Passo 3: 1 % y  (resto da divisão inteira) 
z = (-9 + 1)            # Passo 4: -9 + 1 (adição)
z = -8                  # Passo 5: atribuição
```
É recomendável usar parênteses para deixar evidente qual a ordem das operações. Por exemplo, a expressão de `z` poderia ser escrita mais claramente da seguinte forma:

```python
z = -(x ** 2) + (1 % y)
```

> ### **Exercício - Média de notas**
>
> O programa a seguir calcula a média aritmética de duas notas digitadas pelo usuário.
>
> Escreva-o e teste-o:
>
> ```python
> nota1 = int(input("Digite a nota 1:"))
> nota2 = int(input("Digite a nota 2:"))
> media = (nota1 + nota2) / 2
> print(f"A média é {media}")
> ```
>
> Da forma como está, o programa tem uma limitação importante: **ele só aceita números inteiros!**
>
> 1. Modifique o programa para que ele funcione também com notas com casas decimais.
> 2. Modifique o programa para que ele calcule uma média ponderada: `nota1` deve valer **30%**, e `nota2` deve valer **70%**.
> 3. Modifique o programa que ele calcule a média da disciplina segundo o plano de ensino de Processamento da Informação. Lembre-se de pedir para o usuário digitar o valor do _epsilon_ que deve ser somado à nota.
>
> ***

> ### **Exercício - Ano de nascimento**
>
> Faça um programa que pede o nome do usuário e sua idade (em anos completos). O programa deve então dizer o nome do usuário e seu ano de nascimento.
> 
> Veja um exemplo de execução do programa:
>
> ```
> Qual é o seu nome? Luís Paulo
> Qual é a sua idade? 21
> Luís Paulo, você nasceu no ano 2002.
> ```
>
> ***

> ### **Exercício - Parte inteira e parte fracionária**
>
> Faça um programa que pede ao usuário um número real e então mostra na tela qual é a parte inteira e qual é a parte fracionária do número.
> 
> Veja um exemplo de execução do programa:
>
> ```
> Digite um número real: 36.072
> A parte inteira é 36 e a parte fracionária é 0.072.
> ```
>
> ***

> ### **Exercício - Distância entre duas cidades**
>
> Faça um programa que calcula a distância entre duas cidades.
> No início, o programa deve pedir para o usuário a localização de cada cidade, em km ao longo da rodovia (vamos supor que as cidades são ligadas por uma mesma rodovia).
>
> Veja um exemplo de execução do programa:
>
> ```
> Em qual km da rodovia a cidade 1 está localizada? 34
> Em qual km da rodovia a cidade 2 está localizada? 86
> A distância entre as duas cidades é de 52 km.
> ```
> Observações:
> * Você pode considerar que o km é um número inteiro ou real.
> * A distância entre as duas cidades não pode ser um número negativo.
>
> ***

> ### **Exercício - Equação de segundo grau**
>
> Faça um programa que pede para o usuário três números reais, `a`, `b` e `c`, e então calcula as raízes da equação de segundo grau com duas casas decimais:
>
> $$
> ax^2+bx+c=0
> $$
> 
> Veja um exemplo de execução do programa:
> ```
> Entre com o valor de a: 3
> Entre com o valor de b: 5
> Entre com o valor de c: 2
> As raízes são x1 = -0.67 e x2 = -1.00
> ```
> 
> Dica: use a fórmula de Bhaskara para calcular as raízes:
> 
> $$
> x=\frac{-b\pm\sqrt{b^2-4ac}}{2a}
> $$
> 
> ***

## Funções

Já vimos alguns exemplos do uso de funções em Python. Por exemplo, `abs(x)` é uma função que recebe um valor `x` como argumento e retorna seu valor absoluto.

Por exemplo, no ambiente REPL:

```
>>> x = -5
>>> y = abs(x)
>>> y
5
```

Também vimos a função `max(arg1, arg2, ...)` que recebe uma sequência varíavel de argumentos e retorna o maior entre eles:

```
>>> z = max(10, -2, 32, 4)
>>> z
32
```

Em Python, assim com em outras linguagens de programação, podemos criar nossas próprias funções.

Para exemplificar, vamos criar uma função `soma(a, b)` que recebe dois valores `a` e `b` e retorna a soma `a+b`:

```python
def soma(a, b):
    c = a + b
    return c
```

Podemos agora _chamar_ (isto é, usar) essa função da mesma forma que usamos/chamamos `abs()` ou `max()`. Veja o programa completo:


```python
# Definição da função soma
def soma(a, b):
    c = a + b
    return c

# Exemplo de uso da função soma
x = 2
y = soma(10, x)
print(y) # A saída na tela será 12
```

Em Python, `def` é uma palavra reservada (isto é, é uma palavra que não pode ser utilizada como nome de variável). `def` serve para definir uma função.

Após o `def` devemos escrever o nome da função que estamos definindo. O nome da função segue as mesmas regras de nomenclatura de nomes de variáveis. 

Após escrever o nome da função, colocamos entre parênteses o nome de seus parâmetros separados por vírgula. Os parâmetros são nomes de variáveis que serão criadas com os valores (_argumentos_) de quem chamar a função.

Após os parênteses há um `:` (dois pontos) que sinaliza que nas próximas linhas estão as instruções que fazem parte da função. Entretanto, tais instruções precisam ter uma quantidade fixa de espaços no início na linha (4 espaços em nosso exemplo). Esses espaços são chamados de **identação** ou 
**indentação**. 

As linhas de código com identação indicam que as instruções fazem parte da função. Mais propriamente, dizemos que as instruções, e as variáveis `a` e `b`, fazem parte do **escopo** da função.

Dentro da função temos as seguintes instruções:

```python
    c = a + b
    return c
```

* A primeira linha soma `a` e `b` e guarda o valor em `c`.
* Em seguida, `return c` indica que a função deve retornar com o valor contido em `c`. Assim como `def`, `return` também é uma palavra reservada.

Quando a linha `c = soma(10, x)` é interpretada, a seguinte sequência de instruções é executada pela interpretador:

1. A expressão `soma(10, x)` é identificada como uma **chamada de função**. Nesse momento, a execução do programa é desviada momentaneamente para a linha que contém `def soma(a, b)`;
2. A variável `a` é criada e definida com o argumento `10`;
3. A variável `b` é criada e definida com o valor de `x`, isto é, `2`;
4. A linha `c = a + b` é interpretada;
5. A linha `return c` é interpretada, o que significa que a função deve acabar e retornar o valor de `c`, isto é, `12`;
6. A execução do programa retorna para a linha `y = soma(10, x)`, e agora a expressão `soma(10, x)` é substituída pelo valor retornado pela função, que é `12`. Então, é como se agora `y = soma(10, x)` fosse `y = 12`;
7. A variável `y` é criada com o valor `12`;
8. A linha `print(y)` é interpretada, resultando na impressão de `12` na tela.

Uma observação importante a ser feita é que, no momento em que a função retorna, todas as variáveis que foram definidas em seu escopo deixam de existir. Então, `a`, `b` e `c` deixam de existir.

Agora, se a função for chamada novamente com outros argumentos, as variáveis `a`, `b` e `c` serão criadas novamente no escopo da função.

Também podemos criar uma função sem parâmetros. Por exemplo,

```python
def saudacao():
    """Retorna uma mensagem de saudação."""
    return "Olá!"

print(f"{saudacao()} Seja bem-vindo/a")
```

Observe o uso de um docstring para documentar o que faz a função. É considerada uma boa prática de programação em Python a inclusão de um docstring que explica o que a função faz. O docstring deve explicar para que servem seus parâmetros e o que a função retorna.

Vamos refazer a função `soma()` com docstring e aproveitar para simplificar um pouco suas instruções:

```python
def soma(a, b):
    """Retorna a soma de a e b."""
    return a + b
```

Também podemos definir uma função sem parâmetros e que não retorna nada. Nessa caso, a função acaba quando acabarem as linhas com identação, ou quando a palavra `return` (sem nada à direita) for encontrada:

```python
def imprime_ufabc():
  """Imprime na tela o nome da universidade."""
  print("Universidade Federal do ABC")

def imprime_pi():
  """Imprime na tela o nome da disciplina."""
  print("Processamento da Informação")
  return
  print("Oops, essa linha nunca será alcançada!")

imprime_ufabc()
imprime_pi()
```