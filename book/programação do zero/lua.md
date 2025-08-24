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
  - [3.2: A Linguagem Lua](#32-a-linguagem-lua)



# 3: Lua

Lua é uma linguagem de programação brasileira dinamicamente tipada e interpretada usando bytecode. Rápida, minimalista e poderosa, é muito utilizada como linguagem de extensão em diversos softwares, por ser fácil de integrar. Também é utilizada no desenvolvimento de jogos, sendo a biblioteca [Love2D](https://love2d.org/) a principal escolha. [Roblox](https://pt.wikipedia.org/wiki/Roblox) também a utiliza como linguagem de script para sua engine. Jogos como [Move or Die](https://en.wikipedia.org/wiki/Move_or_Die) e [Balatro](https://www.playbalatro.com/) utilizam Lua. Sua sintaxe é simples e amigável, tornando-a uma ótima escolha para iniciantes.

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

Como disse antes, editores de texto possuem um recurso chamado de destaque de código, que colore o código com certas cores a fim de melhor contrastar os diferentes elementos do mesmo. As cores utilizadas são determinadas através de Temas, e existem várias desses temas com diferentes combinações de cores. Para adicionar um tema no Code, basta instalar a extensão do tema. Uma lista bem grande de diversos temas pode ser encontrado [aqui](https://vscodethemes.com/). Minhas recomendações pessoais são One Dark Pro, Gruvbox Material ou Catpuccin. A maioria dos temas são de modo escuro, embora haja também os de modo claro.





[^1]: IntelliSense é um termo criado pela Microsoft para se referir à um sistema avançado de assistência de código. Originalmente, esse termo foi criado para ser restrito aos ambientes de desenvolvimento proprietários da empresa, mas, com a popularização do termo, começou a ser utilizado globalmente.
IntelliSense é o acrônimo para *Intelligent Sense*, sendo traduzido para *Percepção Inteligente*.
Cada linguagem possui seu próprio motor de assistência, denominado *Language Server*.
*Language Server* e IntelliSense são praticamente sinônimos e se referem à mesma coisa: Um assitente de código avançado.
Um language server detecta erros sintáticos e semânticos ao vivo, enquanto o código está sendo editado.





## 3.2: A Linguagem Lua







<br><br>

- [Próximo Capítulo](./c++.md)
- [Capítulo Anterior](./lógica%20de%20programação.md)
- [Introdução](../introdução.md)
- [Índice](../índice.md)