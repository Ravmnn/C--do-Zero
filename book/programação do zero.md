# 1: Ponto de Entrada
## 1.1: Programação de Computadores

Vivemos em um mundo de certa forma mágico. Com o avanço da tecnologia, surgiram os computadores, máquinas capazes de fazer inúmeras tarefas apenas utilizando o poder da eletricidade, facilitando diversos processos e abrindo portas para revoluções em todas as áreas do globo. No entanto, computadores não são autônomos. Mesmo as Inteligências Artificiais, a nova revolução tecnológica do século, não existem sozinhas. Alguém as criou, alguém as programou. Alguém precisa dizer o que necessita ser feito para um computador, se não, ele irá ficar lá, estático, sem fazer nada. É aí que entra a [Programação de Computadores](https://pt.wikipedia.org/wiki/Programa%C3%A7%C3%A3o_de_computadores), uma verdadeira arte sobre dominar o potencial desses dispositivos eletrônicos.

Programação, no contexto de computação, é o processo de instruir à um computador o que ele deve fazer. Infelizmente, não podemos simplesmente dizer na frente de uma tela: *"Crie um aplicativo de administração de tarefas."* e esperar que as coisas aconteçam. Para instruir um computador e dominá-lo, é necessário nos comunicarmos no mesmo (e único) idioma que um computador entende: [Linguagem de Máquina](https://pt.wikipedia.org/wiki/C%C3%B3digo_de_m%C3%A1quina) (Código de Máquina ou Código Nativo), também conhecido popularmente como Código Binário.





## 1.2: Código de Máquina e as Linguagens de Programação

Código de máquina é um conjunto de instruções que podem ser representados, primariamente, em binário, que é a forma mais análoga ao jeito que os computadores funcionam, ou em outras formas sutilmente mais legíveis, como o sistema hexadecimal. No entanto, ao menos que queira programar todos os programas dos seus sonhos da seguinte forma:

```
0:  b8 0a 00 00 00
5:	bb 14 00 00 00
a:	48 01 d8
d:	48 89 c1
10:	b8 3c 00 00 00
15:	bf 00 00 00 00
1a:	0f 05
```

<small>O techo de código acima é a representação do Código de Máquina em formato hexadecimal. Você definitivamente não precisa entender como interpretar o código acima, nem precisa saber como hexadecimal funciona por enquanto.</small>

Você terá que usar uma [Linguagem de Programação](https://pt.wikipedia.org/wiki/Linguagem_de_programa%C3%A7%C3%A3o).
Uma linguagem de programação é um idioma criado para instruir um computador de forma mais amigável e legível do que usando código de máquina. Programadores na pré-história da computação não possuiam nenhuma linguagem de programação, portanto, usavam uma espécie de cartão perfurado (e outras técnicas) para programar usando o código de máquina puro, pois não havia nenhuma outra forma mais eficiente de ordenar um computador a fazer algo.
Depois de perceberem que o salário deles não valia o trabalho, decidiram inovar um pouco e criar a primeira linguagem de "programação" minimamente legível: [Assembly](https://pt.wikipedia.org/wiki/Linguagem_assembly).

Assembly, embora não possua os recursos nem facilidades para ser chamada de linguagem de programação, revolucionou a forma como os programas de computadores eram escritos na época. Trata-se de uma notação humanamente legível do código de máquina. Eis uma forma mais bela de representar a aberração que foi mostrada acima:

```Assembly
bits 64


section .text

global _start
_start:
    mov rax, 10
    mov rbx, 20
    add rax, rbx

    mov rcx, rax

    ; exit
    mov rax, 60
    mov rdi, 0
    syscall
```

<small>Código Assembly representando literalmente o código anterior, escrito em Código de Máquina. Também não há necessidade de entender o que está acontecendo, apenas aceite que é mais legível que o formato mostrado no início.</small>

Embora Assembly tenha trazido uma incrível facilidade para o programadores da época, a tecnologia foi evoluindo e, com ela, surgiram as linguagens de programação.





## 1.3: Como Computadores Entendem Linguagens de Programação

Talvez você esteja se perguntando como que se pode usar linguagens de programação para comandar um computador, sendo que no início eu disse que o único idioma que um computador entende é o Código de Máquina. Na realidade, tanto Assembly quanto todas as linguagens de programação não existem!
Assembly é convertido em código de máquina por uma ferramenta chamada *Assembler*, então, de certa forma, Assembly em si não existe. Linguagens de programação passam pelo mesmo processo, com algumas diferenças. Existem quatro formas de se fazer uma linguagem de programação conseguir ser entendida pelo computador:

1. *Interpretação*: O código fonte passa por uma ferramenta chamada de interpretador, que executa o código linha por linha em tempo real. É prático, a troco de desempenho.
2. *Compilação Ahead-of-Time*: O código fonte da linguagem passa por uma ferramenta chamada compilador, que a transforma em algum outro código[^1], que pode ser alguma outra linguagem de programação, inclusive. Geralmente, o código original é compilado para Assembly e, em seguida, código de máquina, permitindo que o computador execute o código originalmente escrito em uma linguagem de programação. Esse tipo de compilação é conhecido como *Ahead-of-Time (AOT, adiante do tempo)*, pois primeiro o compila, depois executa. Tende a ser o mais rápido de todos, se bem otimizado.
3. *Compilação Just-in-Time*: O código fonte é compilado em código de máquina enquanto o mesmo está sendo executado, permitindo que apenas certos trechos de código sejam compilados e otimizados. Consequentemente, precisa funcionar em conjunto com um interpretador. Esse tipo de compilação é chamado de *Just-in-Time (JIT, bem no tempo, ao vivo)*, pois compila o código fonte em código de máquina ao vivo, enquanto executa o código interpretado. Geralmente, esse tipo de técnica é incrementada com compilação em bytecode.
4. *Compilação em Bytecode*: O código fonte é compilado em uma representação intermediária chamada de bytecode. O código em bytecode é, então, interpretado por uma máquina virtual, que o simula como se fosse um tipo de código de máquina. É, em sua base, um tipo de interpretação, embora seja mais eficiente que um interpretador puro.

<small>Sei que pode ter parecido complexo. Você pode se aprofundar nessas técnicas quando quiser. Não precisa entender completamente tudo.</small>

Resumindo: Ou o código fonte é transformado em código de máquina, ou ele é executado em tempo real, linha por linha.





## 1.4: As Várias Linguagens

<!-- TODO: add more content -->

Voltando às linguagens, temos muitas opções. Hoje em dia, há dúzias e dúzias de diversas linguagens de programação com estilos e propósitos diferentes. Há, também, linguagens que não foram feitas para programar, mas sim para estruturar dados, entre outros. Como já deve ter percebido, esse livro tem como protagonista a linguagem C++. Não sei como você veio parar aqui, nem por que escolheu C++ como a primeira linguagem. Como já disse na [Introdução](./introdução.md), não é a melhor das escolhas escolhê-la como seu ponto de entrada nesse maravilhoso mundo, devido às suas complexidades que tendem a se tornar obstáculos extras para iniciantes. Todavia, também é sem sentido ter medo de algo que nunca viu, nem experimentou.





# 2: Lógica de Programação
## 2.1: Importância

Antes de botar as mãos na masssa e começar com C++, é de suma importância você ter um fundamento sobre *Lógica de Programação*.
Lógica de programação é o que todas as linguagens de programação no mundo tem em comum. Embora algumas sejam totalmente diferentes entre outras em vários aspectos, todas possuem o mesmo núcleo lógico, ou seja, você acaba usando as mesmas técnicas em todas, claro, adaptando de acordo com a funcionalidade específica da linguagem. A explicação pode ter ficado um pouco confusa, então eis aqui uma analogia à vida real: Lógica de programação é como o que todos os carros tem em comum. Todos os carros aceleram e freiam. Alguns são elétricos, outros possuem marcha automática. Independentemente do quão diferentes uns sejam dos outros, ou da marca e modelo, ambos possuem a mesma funcionalidade base: acelerar e freiar. Entre as linguagens de programação, é a mesma coisa.
Por isso, aprender, nem que seja um pouco, a lógica de programação, pode facilitar seu aprendizado com todas as outras linguagens, lhe poupando tempo para se dedicar nas diferenças de cada uma.





## 2.2: Fundamentos

Por motivos de simplicidade, irei usar uma *Pseudo Linguagem[^2]*.






# 3: C++





[^1]: Muitas pessoas acham que um compilador, na verdade, transforma código de uma linguagem em código de máquina. Isso não é verdade. Um compilador transforma algo em outro. Embora seja possível compilar para Assembly e, em seguida, código de máquina, através de um Assembler. Compilar diretamente para código de máquina não é impossível, mas certamente um desafio e não recomendável.


[^2]: *Pseudo* (do grego, pseudes), é um prefixo muito utilizado em muitas palavras. Significa algo falso, fingido; uma mentira. Nesse caso, pseudo linguagem, significaria linguagem falsa, que não existe de fato.