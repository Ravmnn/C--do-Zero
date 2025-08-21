- [Próximo Capítulo](./lógica%20de%20programação.md)
- [Introdução](../introdução.md)
- [Índice](../índice.md)

<br><br>





- [1: Ponto de Entrada](#1-ponto-de-entrada)
  - [1.1: Bem-vindo](#11-bem-vindo)
  - [1.2: Código de Máquina, Linguagens de Programação, Evolução!](#12-código-de-máquina-linguagens-de-programação-evolução)
    - [1.2.1: Origem de C++ e das Linguagens](#121-origem-de-c-e-das-linguagens)
  - [1.3: Como Computadores Entendem Linguagens de Programação](#13-como-computadores-entendem-linguagens-de-programação)
  - [1.4: As Várias Linguagens](#14-as-várias-linguagens)





# 1: Ponto de Entrada
## 1.1: Bem-vindo

Vivemos em um mundo de certa forma mágico. Com o avanço da tecnologia, surgiram invenções além do entendimento para muitas pessoas. Dentre essas invenções, temos os misteriosos computadores, máquinas capazes de fazer inúmeras tarefas apenas utilizando o poder da eletricidade, facilitando diversos processos e abrindo portas para revoluções em todas as áreas do globo. No entanto, computadores não são autônomos. Mesmo as Inteligências Artificiais, a nova revolução tecnológica do século, não existem sozinhas. Alguém as criou, alguém as programou. Alguém precisa dizer o que necessita ser feito para um computador, se não, ele irá ficar lá, estático, sem fazer nada. É aí que entra a [Programação de Computadores](https://pt.wikipedia.org/wiki/Programa%C3%A7%C3%A3o_de_computadores), uma verdadeira arte sobre dominar o potencial desses dispositivos eletrônicos.

Antes de entrar mais no assunto, é importante deixar claro que você não precisar ser alguém com incríveis capacidades cognitivas para aprender a programar. Por exemplo, talvez você tenha ouvido em algum lugar uma pessoa afirmar que é necessário saber grandes coisas da matemática para aprender a programar. Não é o caso. Embora a matemática seja sim usada na programação, geralmente, em um aplicativo usual, você não precisará saber mais do que operações básicas como soma e subtração. Matemática realmente tende a se tornar um desafio quando o assunto se torna desenvolvimento de jogos, onde é necessário aplicá-la para simular colisões, gerar bons gráficos e  shaders, e na jogabilidade em geral. Se seu intuito ao entrar nesse mundo é se especializar no desenvolvimento de jogos, aí sim dar uma aprofundada na matemática irá lhe ajudar, embora não seja necessário fazê-lo imediatamente. 
Outra coisa que talvez você tenha ouvido falar, é que é necessário ser um verdadeiro fluente em inglês. Você não precisa ser fluente, mas ter uma certa familiaridade vai ajudar, pois *tudo* na programação é escrito na língua inglesa. Mas não se desanime caso seja praticamente um leigo, você pode aproveitar essa oportunidade para ir aprendendo novas palavras com o tempo.
Também é bom deixar claro que é ultra recomendável você ter um computador. Não precisa ser o computador mais recente do mercado. Na realidade, você não terá problemas mesmo se ele tiver por volta de 10-15 anos de idade, embora quanto mais recente, melhor. Programação é leve, dependendo do que for fazer, além de que você não precisa instalar aplicativos pesados para trabalhar com isso. Se seu computador roda um navegador de forma razoável, então não tem nenhum problema.

Assim como em todas as artes, conhecimentos e técnicass no mundo, prática e persistência são os pontos chaves em que você deve focar. Não está conseguindo entender algo? Já leu várias vezes e mesmo assim não compreende? Não tem problema. *O importante é não desistir*.

> “Nossa maior fraqueza está em desistir. O caminho mais certo de vencer é tentar mais uma vez.”
> \- Thomas Edison





## 1.2: Código de Máquina, Linguagens de Programação, Evolução!

Programação, no contexto de computação, é o processo de instruir à um computador o que ele deve fazer. Infelizmente, não podemos simplesmente dizer na frente de uma tela: *"Crie um aplicativo de administração de tarefas."* e esperar que as coisas aconteçam. Para instruir um computador e dominá-lo, é necessário nos comunicarmos no mesmo (e único) idioma que um computador entende: [Linguagem de Máquina](https://pt.wikipedia.org/wiki/C%C3%B3digo_de_m%C3%A1quina) (Código de Máquina ou Código Nativo), também conhecido popularmente como Código Binário.
Note que, hoje em dia, código de máquina não é mais utilizado como forma de programação direta. Ou seja, você não vai escrever 0s e 1s para se comunicar com um computador, embora seja possível.

Código de máquina é um conjunto de instruções que podem ser representados, primariamente, em binário, que é a forma mais análoga ao jeito que os computadores funcionam, ou em outras formas sutilmente mais legíveis, como o sistema hexadecimal. No entanto, ao menos que queira programar todos os programas dos seus sonhos da seguinte forma:

```
0:  b8 0a 00 00 00
5:  bb 14 00 00 00
a:  48 01 d8
d:  48 89 c1
10: b8 3c 00 00 00
15: bf 00 00 00 00
1a: 0f 05
```

*<small>O techo de código acima é a representação do Código de Máquina em formato hexadecimal. Você definitivamente não precisa entender como interpretar o código acima, nem precisa saber como hexadecimal (nem binário) funciona por enquanto.</small>*

Você terá que usar uma [Linguagem de Programação](https://pt.wikipedia.org/wiki/Linguagem_de_programa%C3%A7%C3%A3o).
Uma linguagem de programação é um idioma criado para instruir um computador de forma mais amigável e legível do que usando código de máquina.



### 1.2.1: Origem de C++ e das Linguagens

Lamentavelmente, programadores na pré-história (por volta de 1945) da computação não possuiam nenhuma linguagem de programação, portanto, usavam uma espécie de cartão perfurado (e outras técnicas) para programar usando o código de máquina puro, pois não havia nenhuma outra forma mais eficiente de ordenar um computador a fazer algo.
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

*<small>Código Assembly representando literalmente o código anterior, escrito em Código de Máquina. Na verdade, não sei como programar em código de máquina puro (os que sabem são verdadeiramente raros). O que fiz foi pegar o resultado da compilação do código Assembly acima, feito por um Assembler. Também não há necessidade de entender o que está acontecendo, apenas aceite que é mais legível que o formato mostrado no início.</small>*

Embora Assembly tenha trazido uma incrível facilidade para o programadores da época, sua utilidade foi se tornando mais complicada quando se era necessário criar programas mais complexos, onde era necessário fazer mais com menos, de forma mais eficiente. Essa busca pela eficiência levou os programadores a se pergutarem novamente se o salário deles era o suficiente. Consequentemente, após um tempo, outra evolução no desenvolvimento de softwares foi criada: Fortran, podendo ser considerada a primeira linguagem de programação de alto nível. Depois desse ponto, o desenvolvimento de linguagens se tornou de certa forma comum, o que trouxe várias opções pro mercado da época.

Outro golpe evolucionário seria a criação da linguagem C, por Dennis Ritchie que definitivamente mudou o mundo, mais uma vez. Ela foi criada para o desenvolvimento do sistema operacional Unix, que inspirou totalmente a criação do famoso Linux, também sistema operacional. Não seria exagero falar que C é o que faz praticamente tudo funcionar no mundo dos computadores. Com o tempo, ela se tornou a principal camada após Assembly, o que fez seu uso aumentar. Os principais sistemas operacionais do mercado são feitos em C, embora uma certa quantidade de Assembly seja inevitável. Até mesmo linguagens de prorgamação são criadas em C. Após certo tempo, em 1985, surgiu-se C++, criado por Bjarne Stroustrup, que é como se fosse uma evolução de C, que adicionou novos recursos, sendo a Orientação a Objetos a principal mudança. Hoje em dia, C++ é a principal opção em conjunto com C. Por compilar (compilação será explicado mais a frente) diretamente para Assembly, sua velocidade e desempenho se equivalem. Devido isso, C/C++ é principalmente utilizado onde velocidade de execução é a chave: Jogos, drivers, anti-vírus, sistemas operacionais, bibliotecas gráficas, etc.


> “C facilita você atirar em seu próprio pé; C++ dificulta isso, mas quando acontece, suas pernas vão junto.”
> \- Bjarne Stroustrup

<small>Comentário relacionado àos perigos de manipular memória manualmente, algo necessário tanto em C quanto em C++.</small>





## 1.3: Como Computadores Entendem Linguagens de Programação

Todas as linguagens de programação são apenas texto, sem exceções. Não há absolutamente nenhuma diferença entre a forma como um computador representa este livro e uma linguagem, ambos são apenas texto e, por serem texto, não conseguem fazer nada. Você poderia sem dúvidas apenas criar um arquivo `código.txt` e começar a programar o maior software de todos os tempos em alguma linguagem de sua escolha. Mas aí chegaria o momento em que seria necessário fazer um milagre: Como seria possível fazer um computador entender esse texto? Afinal, no início deste livro, eu disse que o único idioma que um computador entende é o código de máquina. Ou seja, compreender um arquivo de texto na forma de instruções está além de suas capacidades.
Antes de continuar a leitura, pare por alguns segundos e tente imaginar uma forma de fazer um computador, que só entende código de máquina, compreender uma linguagem como C++ que, como já disse, é texto puro.
Encare isso como seu primeiro trabalho como um programador![^1] Não tem problema se errar na resposta, já que ela pode não ser tão simples assim.


Se sua resposta para esse problema foi algo como *"converter o texto em código de máquina"*, meus parabéns, você está nada além de correto.
Assembly, a linguagem que foi introduzida no capítulo anterior, também é texto. Para um computador entender suas instruções representadas por caracteres do alfabeto, todo código escrito em Assembly precisar passar por uma ferramenta chamada de *Assembler*, que converte o código original para código de máquina.

Linguagens de programação, no geral, passam pelo mesmo processo de conversão, com algumas diferenças. Existem quatro formas de se fazer uma linguagem de programação conseguir ser entendida pelo computador:

1. *Interpretação*: O código fonte passa por uma ferramenta chamada de interpretador, que executa o código linha por linha em tempo real. Não há conversão para código de máquina, a lógica da linguagem está completamente integrada no próprio interpretador. O código original é representado na memória utilizando um formato chamado de *Abstract Syntactic Tree (AST, Árvore Sintática Abstrata)*. É prático, a troco de desempenho, já que representar (e converter código em) uma AST tende a ser pesado.
2. *Compilação Ahead-of-Time*: O código fonte da linguagem passa por uma ferramenta chamada compilador, que a transforma em algum outro código[^2], que pode ser alguma outra linguagem de programação, inclusive. Geralmente, o código original é compilado para Assembly e, em seguida, código de máquina, permitindo que o computador execute-o. Esse tipo de compilação é conhecido como *Ahead-of-Time (AOT, adiante do tempo)*, pois primeiro o compila, depois executa. Tende a ser o mais rápido de todos, se bem otimizado.
3. *Compilação Just-in-Time*: O código fonte é compilado em código de máquina enquanto o mesmo está sendo executado, permitindo que apenas certos trechos de código sejam compilados e otimizados. Consequentemente, precisa funcionar em conjunto com um interpretador, já que é necessário a execução em tempo real do código. Esse tipo de compilação é chamado de *Just-in-Time (JIT, bem no tempo; ao vivo)*, pois compila o código fonte em código de máquina ao vivo, enquanto executa o código interpretado. Geralmente, esse tipo de técnica é incrementada com compilação em bytecode.
4. *Compilação em Bytecode*: O código fonte é compilado em uma representação chamada de bytecode. O código em bytecode é, então, interpretado por uma máquina virtual, que o simula como se fosse um tipo de código de máquina. É, em sua base, um tipo de interpretação, embora seja mais eficiente que um interpretador puro, pois o bytecode é mais leve que representar todo o código original com uma AST.

*<small>Sei que pode ter parecido complexo. Você pode se aprofundar nessas técnicas quando quiser. Não precisa entender completamente tudo, já que pode utilizar essas ferramentas sem saber o que acontece por baixo dos panos. No entanto, minha recomendação pessoal é, em algum momento de sua vida, estudar um pouco sobre como funciona o processo de criar linguagens de programação. As técnicas envolvidas podem ajudar em outras áreas. [^3]</small>*

Resumindo: Ou o código fonte é transformado em código de máquina, ou ele é executado em tempo real, linha por linha.





## 1.4: As Várias Linguagens

<!-- TODO: adicionar mais conteúdo -->

Você talvez já tenha percebido ao ler as várias frases desse livro: Não existe uma, duas ou três linguagens de programação, hoje em dia, há dúzias e dúzias de diversas linguagens com estilos e propósitos diferentes. Há, também, linguagens que não foram feitas para programar, mas sim para estruturar dados, entre outros. Para citar algumas, com propósito de exemplificação:
- *Python*, uma das mais populares, com foco em praticidade. Em ocasiões usuais, seria uma das linguagens mais favoritas entre os iniciantes nesse ramo. Hoje muito utilizada na criação de IAs.
- *Javascript*, criado para desenvolvimento de páginas web, embora seja utilizado mais amplamente em outros lugares, como no desenvolvimento de aplicações desktop.
- *C# (C Sharp)*, criado pela Microsoft para o desenvolvimento de aplicações sob o framework[^4] .NET, também da mesma empresa. Muito utilizada no desenvolvimento de jogos com a Game Engine Unity, embora não seja a única a utilizar C#.

Como já deve ter percebido, esse livro tem como protagonista a linguagem C++. Não sei como você veio parar aqui, nem por que escolheu C++ como a primeira linguagem. Como já disse na [Introdução](./introdução.md), não é a melhor das escolhas como seu ponto de entrada nesse maravilhoso mundo, devido às suas complexidades que tendem a se tornar obstáculos extras para iniciantes. Apesar disso, não estou tentando lhe desencorajar, muito pelo contrário, é uma forma de lhe motivar ainda mais. Além do mais, em muitos casos, é sem sentido ter medo de algo que nunca viu.

Esse primeiro capítulo é apenas uma pequena introdução no contexto por trás do mundo da programação. O verdadeiro desafio vem agora. A partir de agora você irá começar a pensar como um programador.





<br><br>

- [Próximo Capítulo](./lógica%20de%20programação.md)
- [Introdução](../introdução.md)
- [Índice](../índice.md)





[^1]: Na programação, seu objetivo é resolver problemas. Sim, resolver problemas. Você já deve ter visto em algum filme ou série um programador ou hacker escrevendo código na velocidade da luz. Na prática, isso não acontece. Primeiramente porque qualidade de código quase sempre irá vencer sobre quantidade. Segundo que a maioria do tempo que você gastar (ou melhor, que deve gastar) em um projeto será lendo código ou o melhorando, não de fato criando vários recursos e funcionalidades.


[^2]: Muitas pessoas acham que um compilador, na verdade, transforma código de uma linguagem em código de máquina. Isso não é verdade. Um compilador transforma algo em outro. Embora seja possível compilar para Assembly e, em seguida, código de máquina, através de um Assembler. Compilar diretamente para código de máquina não é impossível, mas certamente um desafio e não recomendável.


[^3]: Um ótimo livro (grátis) que ensina a criar linguagens de programação: [Crafting Interpreters](https://craftinginterpreters.com/contents.html)


[^4]: Um framework é um conjunto de ferramentas, serviços e bibliotecas com o propósito de auxiliar no desenvolvimento de algo.