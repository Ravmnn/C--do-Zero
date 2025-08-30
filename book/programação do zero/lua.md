- [Próximo Capítulo](./c++.md)
- [Capítulo Anterior](./lógica%20de%20programação.md.md)
- [Introdução](../introdução.md)
- [Índice](../índice.md)

<br><br>





- [3: Lua](#3-lua)
  - [3.1: Setup do Ambiente](#31-setup-do-ambiente)
    - [3.1.1: Interpretador Lua](#311-interpretador-lua)
    - [3.1.2: Terminal](#312-terminal)
    - [3.1.3: Editor de Texto](#313-editor-de-texto)
    - [3.1.4: Sistema de Arquivos](#314-sistema-de-arquivos)
  - [3.2: A Linguagem Lua](#32-a-linguagem-lua)
    - [3.2.1: Mostrando Coisas Numa Tela](#321-mostrando-coisas-numa-tela)



# 3: Lua

Lua é uma linguagem de programação brasileira dinamicamente tipada e interpretada usando bytecode. Rápida, minimalista e poderosa, é muito utilizada como linguagem de extensão (como na criação de plugins) em diversos softwares, por ser fácil de integrar. Também é utilizada no desenvolvimento de jogos, sendo a biblioteca [Love2D](https://love2d.org/) a principal escolha. [Roblox](https://pt.wikipedia.org/wiki/Roblox) também a utiliza como linguagem de script para sua engine. Jogos como [Move or Die](https://en.wikipedia.org/wiki/Move_or_Die) e [Balatro](https://www.playbalatro.com/) utilizam Lua. Sua sintaxe é simples e amigável, tornando-a uma ótima escolha para iniciantes.

Neste capítulo, vamos utilizar a linguagem Lua para aplicar, aprofundar e fixar o conteúdo do capítulo anterior.
A partir daqui, você irá (caso queira) escrever código real e utilizar seu computador para programar. Então, caso esteja lendo este livro em um celular, por exemplo, seria extremamente recomendável o uso de um computador a partir de agora. Caso você de fato não tenha como usar um computador, poderá utilizar algum aplicativo de celular que consiga rodar Lua. Deixarei a pesquisa desses aplicativos em suas mãos.





## 3.1: Setup do Ambiente
### 3.1.1: Interpretador Lua

*<small>Estou assumindo que você está utilizando o sistema operacional Windows, já que é o mais popular no geral. O processo de instalação em outros sistemas operacionais não é muito fora do normal.</small>*

Você tem duas opções: Ou usar a [Versão Online](https://onecompiler.com/lua/) do interpretador, ou instalá-lo: [Interpretador Oficial da Linguagem](https://github.com/rjpcomputing/luaforwindows/releases/download/v5.1.5-52/LuaForWindows_v5.1.5-52.exe). O link acima imediatamente começar a instalar o instalador Windows de Lua. Após instalar, clique no instalador e siga as intruções. Quando acabar, Lua deve estar instalado no seu sistema. A versão acima é a Lua 5.1.5. No momento em que escrevo esta parte, a versão mais recente, e a que está instalada no meu sistema (Linux), é a Lua 5.4.8. No geral, você não deve enfrentar dificuldades com este livro por causa da diferença da versão. Para não complicar as coisas, recomendo ficar com a versão acima mesmo.

Para verificar se já tem Lua instalado ou se sua instalação deu certo, abra o [Terminal](#32-terminal) e digite `lua -v`. Se aparecer uma mensagem como `Lua 5.1.5`, então tudo está certo.



### 3.1.2: Terminal

Todo programador no geral usa extensivamente a famosa ferramenta *terminal*, também conhecida como *prompt de comando* no Windows. Ela é muito útil pois nos permite executar comandos de forma fácil e rápida, uma vez que aprendermos a utilizá-la. Para abrir o terminal no Windows, você pode pressionar o atalho `Win + R`, digitar `cmd` e pressionar `Enter`, que é a forma mais rápida e direta. Você também pode pressionar `Win` e pesquisar por `Prompt de Comando`.

Não se assuste com essa tela preta que é o terminal, você vai se acostumar com ele durante o tempo.



### 3.1.3: Editor de Texto

Um editor de texto é uma ferramenta que auxilia (e muito) ao escrever código. Editores de texto possuem duas funcionalidades principais: Destaque de código, que colore o código de forma que seja fácil identificar o que é o que, e auto-completação, que fornece uma lista de sugestões de completação conforme você vai digitando. Nada lhe impede de usar o tão poderoso bloco de notas do Windows, mas sem dúvidas um editor de texto vai lhe ajudar.

Existe uma grande variedade de editores de texto, sendo [Visual Studio Code](https://code.visualstudio.com/) o mais popular, minha recomendação e o que será utilizado nesse livro. Existem outras opções sólidas e até mais leves, como o [Sublime Text](https://www.sublimetext.com/), mas realmente recomendo usar a opção anterior para seguir junto com o livro.

Editores de texto possuem suporte básico pra praticamente todas as linguagens minimamente conhecidas, então você não precisaria configurar mais nada uma vez que o Code tenha sido instalado. No entanto, certos recursos como o IntelliSense[^1], que é um sistema de assistência muito mais avançado, só são possíveis através de configurações extras. Felizmente, o Code possui um sistema de extensões que nos permite adicionar suporte extra para linguagens de forma fácil e prática. Recomendo instalar a extensão *Lua*, de *sumneko*, para adicionar o suporte de IntelliSense à linguagem Lua.

Como disse antes, editores de texto possuem um recurso chamado de destaque de código, que colore o código com certas cores a fim de melhor contrastar os diferentes elementos do mesmo. As cores utilizadas são determinadas através de Temas, e existem vários desses temas com diferentes combinações de cores. Para adicionar um tema no Code, basta instalar a extensão do tema. Uma lista bem grande de diversos temas pode ser encontrado [aqui](https://vscodethemes.com/). Minhas recomendações pessoais são:

- *One Dark Pro*: Provavelmente o mais popular, com ótimas combinações de cores. Eu costumava a usar esse tema, mas depois de um bom tempo, enjoei dele e procurei algum outro tema mais confortável.
- *Gruvbox Material*: O meu favorito, pois possui cores com uma temperatura mais quente (avermelhado) e suave, o que tende a ser mais confortável para os olhos. Claro, além disso, é muito bonito.
- *Catpuccin*: É praticamente o *One Dark Pro*, mas com cores mais pastéis e suaves. Possui pouco contraste, então pode não ser uma boa opção se você quer preservar sua saúde ocular. Seu nome exótico atrai os amantes de gatos.

A maioria dos temas são de modo escuro, embora haja também os de modo claro. Caso queira alternar de um tema para outro no Code, pressione `Ctrl + Shift + P`. Uma lista com muitas opções deverá aparecer. Cada opção dessa é um comando que faz o Code realizar alguma ação. Para mudar o tema de cor atual, digite `Color Theme`, ou `theme` e escolha a primeira opção. Após isso, outra lista com opções deve aparecer, mostrando os temas instalados.



### 3.1.4: Sistema de Arquivos

*<small>Suponho que você já saiba o básico de como utilizar o explorador de arquivos do Windows.</small>*

O sistema de arquivos é um dos recursos mais essenciais em todo sistema operacional, com o nobre propósito de nos permitir sermos seres racionais e *organizados*[^2]. Organização é extremamente importante na programação. Se você for desorganizado na vida real, não tem problema (tem sim), mas trate de ser organizado na programação. Você não precisa saber em como organizar bem seu código por enquanto, já que você ainda nem começou a escrever um.

De qualquer forma, abra seu explorador de arquivos e crie uma pasta `C++ do Zero` em algum lugar de sua preferência (não em `Downloads`, por favor). Dentro da pasta, crie outra pasta `Lua`. Dentro da pasta `Lua`, crie um arquivo `main.lua`.
A partir daqui, você quer abrir essa pasta `Lua` com o Visual Studio Code. Você tem algumas opções:

- Clicar com o botão direito do mouse na pasta, clicar em `Abrir Com` e achar o Code.
- Abrir o Code e executar o comando `Open Folder` (aperte `Ctrl + K` e, depois, `Ctrl + O`). Então, ache a pasta e abra-a.
- Abrir o Code e arrastar (clicar e segurar) a pasta do explorador de arquivos para a tela do Code.

Se tudo der certo, o Code vai estar com a pasta aberta e você poderá ver o que tem dentro dela no lado esquerdo. Essa divisão é chamada de explorador. Você pode criar arquivos e pastas dentro do próprio Code, ou clicando com o botão direito na área do explorador ou clicando nos ícones em cima do mesmo.
Se você não estiver vendo o arquivo `main.lua`, talvez a pasta `Lua` esteja fechada no explorador. Para abrir/fechar uma pasta, basta clicar nela. Clicar com o botão direito do mouse em um arquivo ou pasta vai abrir uma lista de opções, como remover ou renomear o mesmo. Isso deve ser o suficiente como introdução das capacidades do editor.

Clique no arquivo `main.lua` para abrí-lo. Uma vez aberto, seu conteúdo deve aparecer ao lado direito do explorador, a área que ocupa a maior parte da tela[^3]. Essa área é o que edita o texto em si, e a funcionalidade principal de todo editor de texto.

Pressione `Ctrl + Shift + ´` ou execute o comando `Toggle Terminal`. Isso irá mostrar o terminal embutido do Visual Studio Code. Você pode optar por utilizar o terminal embutido ou o externo.

Independente de qual vá usar, precisará aprender um comando muito importante do terminal: `cd`.
O `cd` serve para navegar entre as pastas do sistema de arquivos. `cd caminhoOuPasta`[^4] vai para dentro de uma pasta, enquanto `cd ..` volta à pasta anterior. Por exemplo, supondo que está utilizando o terminal embutido, verá que a pasta em que o terminal está atualmente é a que você abriu, `C++ do Zero`. Se este for o caso, digite, no terminal, o comando `cd Lua` e pressione `Enter`. Se tudo estiver certo, agora a pasta `Lua` é que vai estar aberta no terminal.

Após isso, escreva outro comando: `lua main.lua`. Se absolutamente nada aconteceu, é porque tudo está certo. O comando anterior chama o interpretador de Lua e o manda executar o código presente no arquivo `main.lua`. Como o arquivo não tem nada, obviamente nada irá acontecer.





## 3.2: A Linguagem Lua
### 3.2.1: Mostrando Coisas Numa Tela

O título desta seção talvez o faça pensar que finalmente iremos criar uma janela e renderizar alguma coisa na tela. Talvez você já esteja empolgado para começar na criação do seu primeiro jogo ou algum aplicativo que tenha em mente. Infelizmente, esse não é o caso. Você com certeza já deve ter visto vários aplicativos e jogos que utilizam uma janela para renderizar botões ou outros elementos gráficos na tela de um computador, mas, criar uma aplicação que faça isso está além dos escopos deste livro, além de ser algo consideravelmente complexo. Nós de fato iremos renderizar coisas na tela, mas de uma forma diferente e limitada, mas prática... Iremos utilizar o terminal.

Há muitos tipos de softwares em que a criação de uma interface gráfica é desnecessária e até mesmo acaba se tornando uma perda de tempo, como é o caso de servidores, drivers, diversas ferramentas de desenvolvimento, como compiladores (como o de C++), interpretadores (como o de Lua), sistemas de versionamento e outras utilidades gerais. Em programas desse tipo, o uso de um simples terminal para exibir e receber informações é o suficiente. Aplicativos que usam o terminal como meio de exibir informações são chamados de, surpreendentemente, aplicativos de terminal.

Agora, como escrevemos caracteres nessa tela preta (cinza, no caso do Code) chamada de terminal? Depende da linguagem utilizada. No caso de Lua, temos a instrução (mais especificamente, a *função*) `print(expression)`.

Creio que você já deva estar com o arquivo `main.lua` aberto no Visual Studio Code, junto com o terminal (externo ou imbutido) aberto na pasta em que `main.lua` está. Caso não esteja, tenha certeza de ler a seção [Sistema de Arquivos](#314-sistema-de-arquivos). Caso tudo esteja certo, escreva no arquivo:


```Lua
print("Mão na massa!")
```


E então use o comando `lua main.lua`, que já lhe foi apresentado, para executar o código. Se o texto `Mão na massa!` tiver sido escrita no seu terminal, então realmente tudo está funcionando. Parabéns, você programou seu primeiro programa em Lua!

Vamos desconstruir a linha de código acima:
1. `print`: É a função em Lua que escreve coisas no terminal. Funções serão melhor abordadas ainda neste capítulo.
2. `(` e `)`: Toda função começa e termina com `(` e `)`, respectivamente.
3. `"Mão na massa!"`: Como foi dito em [Lógica de Programação - Tipos de Dados Primitivos](lógica%20de%20programação.md#21-tipos-de-dados-primitivos), é uma string (texto), pois está entre aspas `"`.

Você pode por qualquer [expressão](lógica%20de%20programação.md#22-expressões) entre o `(` e `)` de `print`. Experimente inserir expressões diferentes, como soma de números, expressões condicionais ou valores literais em `print`s diferentes. Não se esqueça que prática é extremamente importante para aprender a programar, não seja tímido!





[^1]: IntelliSense é um termo criado pela Microsoft para se referir à um sistema avançado de assistência de código. Originalmente, esse termo foi criado para ser restrito aos ambientes de desenvolvimento proprietários da empresa, mas, com a popularização do termo, começou a ser utilizado globalmente.
IntelliSense é o acrônimo para *Intelligent Sense*, sendo traduzido para *Percepção Inteligente*.
Cada linguagem possui seu próprio motor de assistência, denominado *Language Server*.
*Language Server* e IntelliSense são praticamente sinônimos e se referem à mesma coisa: Um assistente de código avançado.
Um language server detecta erros sintáticos e semânticos ao vivo, enquanto o código está sendo editado.


[^2]: Bem... No caso do funcionamento de um sistema operacional, um sistema de arquivos é necessário para guardar coisas no disco e usá-los depois.


[^3]: Você pode redimensionar as divisões colocando o mouse entre uma e outra, segurando o botão esquerdo e o movendo.


[^4]: É possível entrar em várias pastas de uma vez separando-as por `\`. Por exemplo, `cd project\source\core`. Essa notação é chamada de *caminho* (ou *path*, em inglês).





<br><br>

- [Próximo Capítulo](./c++.md)
- [Capítulo Anterior](./lógica%20de%20programação.md)
- [Introdução](../introdução.md)
- [Índice](../índice.md)