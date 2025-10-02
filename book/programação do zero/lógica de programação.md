- [Próximo Capítulo](./lua.md)
- [Capítulo Anterior](./ponto%20de%20entrada.md)
- [Introdução](../introdução.md)
- [Índice](../índice.md)

<br><br>





- [2: Lógica de Programação](#2-lógica-de-programação)
  - [2.1: Tipos de Dados Primitivos](#21-tipos-de-dados-primitivos)
  - [2.2: Expressões](#22-expressões)
    - [2.2.1: Expressões Aritméticas](#221-expressões-aritméticas)
    - [2.2.2: Expressões Condicionais](#222-expressões-condicionais)
  - [2.3: Precedência de Operadores](#23-precedência-de-operadores)
  - [2.4: Instruções de Controle Básicas](#24-instruções-de-controle-básicas)
    - [2.4.1: Instrução `if`](#241-instrução-if)
    - [2.4.2: Instrução `while`](#242-instrução-while)
  - [2.5: Variáveis](#25-variáveis)
  - [2.6: Tipagem](#26-tipagem)
  - [2.7: Mãos na Massa.](#27-mãos-na-massa)





# 2: Lógica de Programação

Antes de botar as mãos na masssa e começar com C++, é de suma importância você ter um fundamento sobre *Lógica de Programação*. Na realidade, após este capítulo, ainda não iremos brincar com C++. Muitas das informações presentes aqui podem ficar meio vagas e serem abstratas demais, então julguei que começar com uma linguagem mais simples, com o intuito de fixar o conteúdo aprendido aqui, seria uma boa ideia. A linguagem escolhida é Lua, ela será melhor explicada no próximo capítulo.

Lógica de programação é o que todas as linguagens de programação no mundo tem em comum. Embora algumas sejam totalmente diferentes entre outras em vários aspectos, todas possuem o mesmo núcleo lógico, ou seja, você acaba usando as mesmas técnicas em todas, claro, adaptando de acordo com a funcionalidade específica da linguagem. A explicação pode ter ficado um pouco confusa, então eis aqui uma analogia à vida real: Lógica de programação é como o que todos os carros tem em comum. Todos os carros aceleram e freiam. Alguns são elétricos, outros possuem marcha automática. Independentemente do quão diferentes uns sejam dos outros, ou da marca e modelo, ambos possuem a mesma funcionalidade base: acelerar e freiar. Entre as linguagens de programação, é a mesma coisa.
Por isso, aprender, nem que seja um pouco, a lógica de programação, pode facilitar seu aprendizado com todas as outras linguagens, lhe poupando tempo para se dedicar nas diferenças de cada uma.

Durante esse capítulo, vou utilizar bastante frases como "linguagens de programação ..." ou "toda linguagem de programação ..." com o intuito de englobar a *maioria* das linguagens de programação, já que pode haver alguma que não se encaixa na afirmação seguinte.





## 2.1: Tipos de Dados Primitivos

Números são incríveis. Por que? Computadores entendem apenas duas coisas: números e números. Isso significa que, se queremos representar algo que não possa ser representado por um número (como um texto), devemos dar um jeito de fazer o mesmo conseguir ser representado por um. As cores que você enxerga em uma tela, o texto desse livro, os vários elementos que um jogo pode ter, a interface gráfica de um sistema operacional... Todas essas coisas são representadas internamente por números, mesmo que não pareça. Mais uma pergunta pra você, use alguns segundos da sua vida para pensar em uma resposta: Como você representaria o texto `pedra` usando apenas números?

Se sua resposta foi algo como "Criar uma tabela em que cada número representa uma letra do alfabeto", parabéns, você pensa como um computador. Não podemos representar letras diretamente em um computador, mas podemos usar uma alternativa inteligente e mapear cada caractere do alfabeto à um número. Essa é a abordagem utilizada por todos os computadores internacionalmente para representar letras e textos. [ASCII](https://pt.wikipedia.org/wiki/ASCII) (*American Standard Code for Information Interchange* ou *Código Padrão Americano para o Intercâmbio de Informação*, em português) é uma tabela que mapeia todos os caracteres comuns[^1] latinos à um número. Utilizando esse princípio, o texto da pergunta feita acima poderia ser representado da seguinte maneira, utilizando ASCII:


```
p   e   d   r   a
112 101 100 114 97
```


Cores também são representadas utilizando uma combinação de números, sendo o principal formato o [RGB](https://pt.wikipedia.org/wiki/RGB) (Red, Green, Blue), onde a combinação de diferentes intensidades da cor vermelha, verde e azul conseguem resultar em uma variedade astronômica de cores.

Embora tudo em um computador seja representado por números, linguagens de programação atribuem à um valor um tipo específico. Isso é importante porque, se não houvesse uma forma de saber com que tipo de valor estamos trabalhando ao criar um programa, poderíamos acabar tratando um caractere como se fosse um número comum. Imagine o caos que somar dois caracteres, pensando serem números comuns, poderia causar. Por exemplo, no famoso jogo Minecraft, não podemos tratar um animal como um bloco. Da mesma forma, não podemos tratar um número como se fosse um texto[^2], embora ambos sejam números por baixo dos panos.
Os tipos de dados que uma linguagem possui depende dela, embora seja quase certo que toda linguagem possua os seguintes tipos:

- Integer: Representa um número inteiro, que não possui vírgula, como `10`, `123`, `7`, `-3`, `0`. Geralmente, o nome desse tipo é abreviado para `int`.
- Float: Representa um número que possui vírgula[^3], como `10.123`, `3.14159`, `-0.0825`
- Boolean: Representa valores lógicos que podem ser `true` (verdadeiro) ou `false` (falso). É utilizado para expressar condições. Por exemplo, `o número 4 é igual à soma 2 + 2?` resultaria em `true`. Geralmente abreviado para `bool`.
- String: Representa texto. Textos em linguagens de programação são colocados entre aspas `"`. Algumas usam aspas simples `'` também. Exemplo: `"Isso é literalmente um texto"`.

*<small>Note que os nomes dos tipos estão em inglês propositalmente. Elas estarão assim também em praticamente todas as linguagens.</small>*

Valores como `10`, `4.151`, `true` e `"texto"` também são chamados de *literais*, pois representam valores, literalmente.

Esses tipos de dados são chamados de *primitivos* porque são a base de todos os outros dados, ou seja, é possível criar outros tipos de dados juntando eles. Toda linguagem de programação possui algum mecanismo que permita a criação de novos tipos. Esse recurso será abordado melhor mais a frente (no próximo capítulo).



## 2.2: Expressões

Em uma linguagem de programação, *expressão* é tudo aquilo que gera um resultado. Por exemplo, a soma de dois números é uma expressão, pois gera um resultado final. Valores literais, como `123` e `true` também são expressões. A maioria das expressões utilizam *operadores*, que são identificadores que determinam que tipo de expressão está sendo executada, e *operandos*, que são os valores que serão processados de alguma forma.

Essa seção é um pouco complexa e praticamente um monte de tabelas explicando as expressões mais comuns. Você não precisa necessariamente decorar nada daqui, pois vou tentar aplicar todo o conteúdo a partir daqui no próximo capítulo. De qualquer forma, leia com atenção e cuidado.



### 2.2.1: Expressões Aritméticas

Bons exemplos de uma expressão seriam cálculos aritméticos:

<!-- TODO: falar sobre precedência -->


- `left + right`: Soma;
- `left - right`: Subtração;
- `left * right`: Multiplicação;
- `left / right`: Divisão.


Exemplos:
`5.5 + 3` | `10 - 4.25 - 2` | `2 * 3.5 * 4`
`20 / 2.5` | `7.5 + 2 * 3` | `(5 + 2.5) * 3.5`
`8.5 - 2.25 - 1` | `(4 + 1.5) * (3 - 2.5)`
`10.5 / (2 + 3.5)` | `(6 - 2.5) * 4 / 2`


No trecho `5.5 + 3`, `5.5` e `3` são operandos, enquanto `+` é o operador.
Note que em expressões como `(5 + 2.5) * 3.5`, são utilizados parênteses. Isso será explicado mais a frente.


### 2.2.2: Expressões Condicionais

Na seção [Tipos de Dados Primitivos](#221-tipos-de-dados-primitivos), você foi apresentado ao tipo `bool`, que representa os valores `true` ou `false`. A utilidade desse tipo de dado se torna mais visível quando estamos falando de comparação condicional. Por exemplo, na condição `se eu dividir 10 por 2, o resultado será 5?`, qual você acha que seria a resposta? `true` ou `false`?
Nesse caso, temos o resultado sendo `true`.
Note que o resultado de uma expressão condicional sempre será um valor do tipo `bool`.

Linguagens de programação aceitam comparações desse tipo, embora a forma como se escreva o exemplo acima seja `10 / 2 == 5`.
Irei utilizar uma tabela para representar o resultado das expressões para certos operandos.


- `left == right`: `left` é igual a `right`?

| left         | right    | result  |
| ------------ | -------- | ------- |
| `2`          | `2`      | `true`  |
| `5`          | `3`      | `false` |
| `"cachorro"` | `"gato"` | `false` |
| `true`       | `true`   | `true`  |

<br><br>



- `left != right`: `left` é diferente de `right`?

| left         | right    | result  |
| ------------ | -------- | ------- |
| `7`          | `2`      | `true`  |
| `5`          | `5`      | `false` |
| `"cachorro"` | `"gato"` | `true`  |
| `true`       | `false`  | `true`  |

<br><br>



- `left > right`: `left` é maior que `right`?

| left  | right | result  |
| ----- | ----- | ------- |
| `15`  | `2`   | `true`  |
| `-5`  | `-8`  | `true`  |
| `100` | `100` | `false` |
| `0`   | `1`   | `false` |

<br><br>



- `left < right`: `left` é menor que `right`?

| left  | right | result  |
| ----- | ----- | ------- |
| `98`  | `97`  | `false` |
| `200` | `320` | `true`  |
| `5`   | `10`  | `true`  |
| `-9`  | `-4`  | `true`  |

<br><br>



- `left >= right`: `left` é maior ou igual a `right`?

| left | right | result  |
| ---- | ----- | ------- |
| `1`  | `1`   | `true`  |
| `32` | `84`  | `false` |
| `6`  | `5`   | `true`  |
| `0`  | `0`   | `true`  |

<br><br>



- `left <= right`: `left` é menor ou igual a `right`?

| left  | right | result  |
| ----- | ----- | ------- |
| `30`  | `20`  | `false` |
| `200` | `100` | `false` |
| `1`   | `6`   | `true`  |
| `1`   | `-1`  | `false` |

<br><br>



- `!value`: Inverso de `value`. Também pode ser lido como "`value` é igual a `false`?".

| value   | result  |
| ------- | ------- |
| `true`  | `false` |
| `false` | `true`  |

Algumas linguagens usam `not` para representar o operador em vez de `!`: `not true` resultaria em `false`.

<br><br>



- `left && right`: Tanto `left` quanto `right` são `true`?

| left    | right   | result  |
| ------- | ------- | ------- |
| `true`  | `true`  | `true`  |
| `true`  | `false` | `false` |
| `false` | `true`  | `false` |
| `false` | `false` | `false` |

Algumas linguagens usam `and` para representar o operador em vez de `&&`: `2 == 2 and 5 > 2` resultaria em `true`.

<br><br>



- `left || right`: Entre `left` e `right`, algum deles é `true`?

| left    | right   | result  |
| ------- | ------- | ------- |
| `true`  | `true`  | `true`  |
| `true`  | `false` | `false` |
| `false` | `true`  | `false` |
| `false` | `false` | `false` |

Algumas linguagens usam `or` para representar o operador em vez de `||`: `true or false` resultaria em `true`.

<br><br>




Ufa! Como disse antes, você não precisa se desesperar em decorar nada daqui, dar uma olhada básica já será o suficiente.

Note que você pode ter várias outras expressões dentro de uma expressão:
- `(32 + 68 == 100 && !false) != (9 / 3 * 10 == 30)`


Tente visualizar o que acontece na expressão acima e calcule tudo mentalmente!

<details>
<summary>Resultado:</summary>

`32 + 68 == 100`: `true`
`!false`: `true`

`true && true`: `true`

`9 / 3 * 10 == 30`: `true`

`true != true` resulta em `false`, que é o valor final da expressão.
</details>

<br><br>



## 2.3: Precedência de Operadores

Na matemática, certas operações vem primeiro que outras. Por exemplo: `2 + 5 * 2` resulta em `12`, não `14`. Isso porque as operações de multiplicação e divisão ocorrem antes das de soma e subtração. Linguagens de programação também seguem essa regra, mas a expandem para todos os operadores e expressões possíveis na linguagem.
A ordem no qual expressões são calculadas é chamada de precedência. A precedência de expressões varia de acordo com a linguagem, então a única forma precisa de saber a ordem no qual uma expressão calcula seus operandos é consultando a documentação oficial da linguagem, apesar de ser possível ter uma ideia geral, seguindo a seguinte ordem:

1. Valores literais
2. `!`
3. `*` e `/`
4. `+` e `-`
5. `>`, `<`, `>=` e `<=`
6. `==` e `!=`
7. `&&` e `||`

*<small>Note que a lista acima está longe de encobrir todas as expressões de uma linguagem real.</small>*

É possível fazer com que uma expressão seja calculada antes de todas as outras usando a expressão de agrupamento `(expression)`. Ela segue a mesma lógica que na matemática: Primeiro resolva os cálculos entre parênteses, depois o resto.
Caso você queira que `10 + 5 * 3` resulte em `45` em vez de `25`, reescreva agrupando a expressão de soma: `(10 + 5) * 3`.





## 2.4: Instruções de Controle Básicas


Até aqui, você foi apresentado aos tipos de dados e várias expressões que geram diferentes resultados com base em seus operandos. Expressões são fundamentais, mas você não consegue fazer grandes coisas apenas utilizando elas. É aí que entram as instruções.

Uma instrução, como o nome já diz, instrui o computador a fazer alguma coisa, geralmente, com base em algum valor (ou expressão). A maioria das instruções de uma linguagem alteram o que chamamos de [Fluxo de Controle](https://pt.wikipedia.org/wiki/Estrutura_de_controle) (ou Fluxo de Execução).

Fluxo de controle é a ordem pelo qual as instruções serão executadas. Por padrão, as instruções são lidas de cima pra baixo, o que corresponde, em um arquivo de texto, das menores linhas para as maiores:

```
primeiro
segundo
terceiro

...
```

Podemos, por exemplo, criar algumas instruções de exemplo para simular a rotina de ir dormir de alguém:

```
jantar

irProBanheiro
tomarBanho
escovarOsDentes
sairDoBanheiro

irProQuarto
dormir
```


No exemplo acima[^4], cada linha é uma instrução. Em uma linguagem de programação real, há também instruções que usam mais de uma linha, quando necessário.

Em um programa real, não dá pra ser tão linear assim. Programas precisam tomar decisões com base em muitos fatores, realizando certa ação apenas quando uma condição é alcançada. Muitas vezes, também é necessário executar o mesmo pedaço de código muitas vezes em sequência. As principais instruções responsáveis por realizar os dois comportamentos que acabei de dizer (tomada de decisões e loops), são o `if` e o `while`, respectivamente.
Note que eu as caracterizei como instruções "principais", logo, não são as únicas[^5].



### 2.4.1: Instrução `if`

A instrução `if` executa um trecho de código apenas *se* a condição especificada for verdadeira. `if` é provavelmente a mais importante de todas as outras instruções, pois é a única forma de ter um programa que toma decisões. Ela vem junto com outras duas instruções *opcionais* que fazem parte de si: `else` e `else if`, que, ao contrário de `if`, executam código caso a condição do `if` anterior seja falsa. `else if` executa um código *se a condição anterior tiver falhada e a condição atual for atendida*. `else` executa um código *se todas as condições anteriores não tiverem sido atendidas*.
Utilizando o `if` e suas instruções complementares, podemos criar um pequeno algoritmo que categoriza uma pessoa de acordo com a idade dela:

```Lua
if idade < 4
    bebê

else if idade < 12
    criança

else if idade < 18
    adolescente

else
    adulto
    
```

*<small>Note que o techo de código acima é uma [Pseudo Linguagem](https://pt.wikipedia.org/wiki/Pseudoc%C3%B3digo)[^6], que é utilizada apenas por motivos de demonstração e não representa nenhuma linguagem real. Além disso, não esqueça que linguagens de programação são apenas texto e podem ser escritas dentro de arquivos convencionais.</small>*

No código acima, a instrução `if` vai executar o código `bebê` apenas se a expressão condicional `idade < 4` resultar em `true`. Caso esse não seja o caso, o programa irá checar se a condição `idade < 12` em `else if` é verdadeira. Se for, então o código respectivo à instrução (nesse caso, `criança`) será executado. Se ainda não for o caso, uma outra checagem será feita na condição seguinte. Se todas as condições falharem, o código a ser executa será o que estiver no `else`.

Como disse antes, tanto `else if` quanto `else` são opcionais. A instrução `else if` pode aparecer quantas vezes você quiser após o `if`, enquanto o `else` só pode aparecer uma única vez, no final.



### 2.4.2: Instrução `while`

A instrução `while`[^7] repete certo trecho de código *enquanto* uma condição for verdadeira. `while` também possui instruções complementares: `continue` e `break`. `continue` volta imediatamente para o início do loop. `break` para o loop imediatamente. Podemos usar o `while` para criar um algoritmo que simula um carro na vida real:

```Lua
turnCarOn

while carIsOn
    if stopLightIsOn
        brakeAndStop
        continue

    if carVelocity < 40
        accelerate
```

*<small>Irei usar inglês a partir de agora ao representar código.</small>*





## 2.5: Variáveis

*Variáveis são locais alocados na memória que armazenam um valor específico...*
Isso é o que um engenheiro de software provavelmente iria responder se você perguntasse o que é uma variável para ele. Em palavras mais simples, uma variável é um nome que armazena um valor.

Dados precisam ser armazenados em algum lugar para de fato serem úteis. Variáveis cumprem esse papel de forma digna. Caso você queira guardar um valor para processá-lo, ou apenas lê-lo depois, você terá que usar uma variável.

A forma como uma variável funciona em uma linguagem de programação é extremamente variável (haha...). Algumas linguagens o obrigam a definir o tipo de uma variável no momento em que ela é criada, proibindo a atribuição de um valor de tipo diferente (tipagem estática), enquanto outras não se importam (tipagem dinâmica. Tipagem será explicado mais a frente). Algumas linguagens usam instruções para criar uma variável, enquanto outras não precisam. Algumas linguagens definem uma variável como imutável, ao menos que se especifique o contrário, no momento em que é criada, enquanto outras definem variáveis como mutáveis por padrão.

Independentemente da forma como uma variável funciona em determinada linguagem de programação, podemos ter uma ideia geral da forma como se cria uma: `name = value`. O valor de uma variável pode ser alterado após sua criação.

```Lua
x = 10
y = 15

result = x + y
```

Consegue me dizer qual é o valor da variável `result`?

<details>
<summary>Resultado:</summary>

No código acima, crio três variáveis: `x`, iniciado com o valor `10`; `y`, com o valor `15`; `result`, com a soma das outras duas variáveis. Aonde o nome de uma variável aparecer, é como se o seu valor fosse substituído no local do nome: `result = 10 + 15`, logo, `result = 25`.
Simples, não?

</details>

<br><br>

Variáveis serão melhor abordadas quando começarmos a usar uma linguagem real, que será Lua.





## 2.6: Tipagem

Tipagem determina como uma linguagem de programação trabalha com os tipos de dados existentes.
Existem três tipos de tipagem:

- Tipagem Dinâmica: Linguagens com tipagem dinâmica são mais permissivas a respeito do tipo de valores. Por exemplo, ao criar uma variável, você não precisa especificar seu tipo, e a linguagem permite a variável armazenar valores de tipos diferentes durante a execução do programa. Por conta disso, a linguagem pode ser considerada mais "solta". Isso tende a ser prático, mas pode trazer problemas a longo prazo, pois ser tão permissivo a respeito dos tipos de dados aumenta a probabilidade de criar bugs no código. Por exemplo, muitas vezes queremos que uma variável guarde um valor de um tipo específico. Mas, em uma linguagem dinamicamente tipada, isso não é simples.
Exemplos de linguagens dinamicamente tipadas incluem: Python, Javascript e Lua.
- Tipagem Estática: É o inverso de tipagem dinâmica. Linguagens estaticamente tipadas são rígidas a respeito dos tipos de dados. Variáveis precisam ter um tipo definido desde a sua criação, proibindo o armazenamento de um valor de tipo diferente. Essa rigidez e restrição deixa a linguagem mais segura e previsivel, além de evitar os bugs em que a tipagem dinâmica está sujeita. Pessoalmente, prefiro tipagem estática em vez de dinâmica.
A maioria das linguagens populares são estaticamente tipadas. C/C++, C#, Java, Swift, Go, Rust e muitas outras.
- Tipagem Gradual: É o equilíbrio entre tipagem estática e dinâmica. O programador pode escolher quando usar um tipo especifico ou não. Python e Typescript[^8] são dois ótimos exemplos de tipagem gradual, principalmente Typescript.





## 2.7: Mãos na Massa.

Creio que com esta pequena introdução você esteja preparado para ir pro próximo nível. Como disse no início deste capítulo, não vamos começar com C++, mas sim com Lua. A partir daqui, você irá escrever código de verdade, empolgue-se!






<br><br>

- [Próximo Capítulo](./lua.md)
- [Capítulo Anterior](./ponto%20de%20entrada.md)
- [Introdução](../introdução.md)
- [Índice](../índice.md)






[^1]: ASCII encobre um total de 255 caracteres possíveis. No entanto, vivemos em um mundo onde o alfabeto latino não é o único. Temos uma quantidade espetacular de alfabetos diferentes, cada um contendo uma quantidade variável de caracteres. Para resolver o problema de que não seria possível mapear todos os alfabetos do mundo pelo ASCII, foi criado o [Unicode](https://home.unicode.org/), uma tabela mais universal com o objetivo de tornar possível a utilização de todos os alfabetos do mundo em um computador.


[^2]: Sabia que os números que estão no teclado do seu computador são tratados como texto, e não números de fato?


[^3]: Na maioria das linguagens, a vírgula de um número fracionário é representado por um ponto `.`.


[^4]: Perceba que nas instruções do exemplo, utilizo um estilo de nomenclatura onde a primeira letra de cada palavra (com exceção da primeira palavra) é em maiúscula, enquanto o resto continua em minúsculo. Esses tipos de nomenclatura são muito comuns em linguagens de programação, onde não se pode usar o caractere de espaço ` ` tão livremente. Cada estilo de nomenclatura possui um nome. No caso do estilo utilizado no exemplo, chama-se *Camel Case*. Uma lista dos estilos de nomenclatura pode ser encontrado [aqui](https://en.wikipedia.org/wiki/Naming_convention_(programming)).


[^5]: A maioria das linguagens possuem outras instruções como `for`, `foreach`, `do ... while` e `loop` no caso de loops; `switch` e `match`, no caso de tomada de decisões. O mais interessante dessas instruções é que seus comportamentos podem ser recriados a partir do (e, em algumas linguagens, são literalmente convertidos para) `while` ou `if`. A existência de instruções como essas, que derivam de instruções bases, tem como objetivo aumentar a praticidade e deixar código mais legível.


[^6]: Uma Pseudo Linguagem é apenas um texto que se assemelha a alguma linguagem real, com o propósito de demonstrar exemplos de código. Pseudo é uma palavra de origem grega que significa "falso", "fingido" ou "de mentira". No exemplo de "Pseudo Linguagem", sua tradução seria "Linguagem Falsa".


[^7]: Por incrível que pareça, uma das maiores utilidades do `while` é criar um loop infinito (ou um que dure muito tempo). Por exemplo, em jogos, é comum o termo "game loop", que se refere ao `while` que fica executando toda a lógica do jogo de novo e de novo. Caso ainda não tenha percebido, um loop infinito pode ser criado com `while true ...`.


[^8]: Typescript é uma linguagem de programação criado pela Microsoft e é literalmente Javascript com suporte para tipagem gradual. Como Javascript ganhou muita popularidade e começou a ser utilizado amplamente para desenvolver coisas que não foi feito para desenvolver, percebeu-se a necessidade de adicionar um sistema de tipos mais seguro para a linguagem, já que a linguagem pura é totalmente dinamicamente tipada. Foi aí que surgiu Typescript.