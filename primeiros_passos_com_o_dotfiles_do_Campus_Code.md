# Primeiros passos com o dotfiles da Campus Code

Faz pouco mais de dois anos que decidi utilizar sistemas operacionais Linux no
meu dia a dia. A decisão surgiu de um recente entusiasmo por tecnologias open
source, e pela sensação de que desenvolvedores encontravam em ambientes Linux,
maior liberdade para customização do ambiente de trabalho, e ferramentas mais
maduras. Essas sensações me levaram a crer que eu poderia ser mais produtivo
utilizando plataformas Linux.

Eu demorei um pouco para encontrar a produtividade que eu estava procurando.
Minhas customizações do sistema eram basicamente visuais, temas e icones. As
ferramentas que eu utilizava eram praticamente as mesmas de quando eu ainda era
um usuario Windows.

Foi durante meu treinamento na Campus Code que eu tive o meu primeiro vislumbre
do que eu estava realmente procurando. Observando o Alan Batista e o João
Almeida utilizando o Vim e o terminal eu percebi que havia algo diferente ali.
Sempre foi tão complicado pra mim utilizar o Vim, e eles realizavam tarefas
complexas de forma tão ágil e aparentemente simples. Logo eles me explicaram que
aquilo era reflexo dos dotfiles da Campus em ação. Inserindo atalhos e novas
funcionalidades as ferramentas padrões do sistema.

### O que são dotfiles?

Mas afinal, o que é um dotfile? O termo dotfile tem origem nos arquivos de
configurações de sistemas Unix-Like. No Ubuntu se você rodar o comando `ls -a`
na pasta home do seu usuário, você vera alguns desse arquivos, como por exemplo
o **.aliases**. Esses arquivos de configurações são utilizados tanto pelo sistema,
quanto por programas. Normalmente são arquivos de texto simples, sempre com o
nome do arquivo iniciando com um ponto. O ponto no inicio do arquivo indica que
não se trata de um arquivo "normal", e por padrão ele é não exibido ao usuário.

Em resumo um dotfile é um arquivo de configuração onde você pode ajustar o
comportamento do seu SO e programas. O usuário pode moldar o ambiente de
trabalho de forma a atender suas necessidades e peculiaridades.

Logo quando se fala em dotfiles de alguem, estamos falando do conjunto de
arquivos de configuração que essa pessoa construiu para moldar seu ambiente aos
seus gostos e preferencias. Muitas pessoas publicam seus dotfiles em
repositórios públicos. E muitos deles criam uma instalação automatizada para
instalar programas e plugins necessários ao ambiente.

### Campus Code Dotfiles

Os dotfiles da Campus estão disponibilizados no GitHub no link:
https://github.com/campuscode/cc_dotfiles

No readme do projeto você verá que o cc_dotfiles foi baseado nos dotfiles do Yan
Pritzker e nos da Thoughtbot. Lá você encontra o link para esses dois projetos.

O cc_dotfiles foi configurado para auxiliar no uso do terminal e do vim como
ambiente para desenvolvimento, principalmente utilizando o Ruby como linguagem.
Mas ele pode facilmente ser utilizado como base para criar outras configurações
para suporte a outras linguagens e ferramentas.

Algumas das ferramentas que o cc_dotfiles utiliza para compor o ambiente:

- [zsh](http://www.zsh.org/)
- [tmux](https://tmux.github.io/)
- [Silver Searcher](https://github.com/ggreer/the_silver_searcher)
- [rvm](https://rvm.io/)
- Vim Gnome (Linux), MacVim (iOS)

#### Instalando o cc_dotfiles no Ubuntu

No readme do projeto temos o seguinte comando para executar a instalação
automatizada: `sh -c "'curl -fSs https://raw.githubusercontent.com/campuscode/cc_dotfiles/master/install.sh'"`
. Mas antes de executarmos esse comando é preciso suprir algumas dependencias
do instalador.

Primeiro vamos atualizar o repositório do sistema com o comando:

```
sudo apt-get update
```

Agora precisamos instalar o `curl` para realizar o download do script de
instalação:

```
sudo apt-get install curl
```

Após o `curl` instalado, precisamos do `git` para que o script seja capaz de
clonar os arquivos do projeto. Rode então o comando de instalação:

```
sudo apt-get install git
```

A última dependencia da instalação é o `Ruby`. Os scripts utilizam uma **Rake**
para executar passos da instalação. Para instalar o ruby execute:

```
sudo apt-get install ruby
```

Agora com as dependencias supridas podemos rodar o comando de instalação dos
dotfiles:

```
sh -c "`curl -fSs https://raw.githubusercontent.com/campuscode/cc_dotfiles/master/install.sh`"
```

Após rodar esse comando o script de instalação será baixado e irá instalar as
dependencias dos dotfiles. Uma delas é o `rvm`. Eventualmente pode ser requerida
sua senha para executar a instalação do `rvm`.

Um outro passo da instalação do cc_dotfiles que pode requerer a interação do
usuário é o processo de instalação de plugins no vim. É provável que aparece uma
mensagem de erro relacionado a sintaxe de algum arquivo, basta apertar a tecla
`enter` que o processo de instalação de plugins no vim irá proceguir.

O solarized é um tema de cores para o seu terminal. O script do cc_dotfiles
executa o scrip para instalação do tema. O processo de instalação do solirazed é
bem simples, primeiro ele te pergunta qual dos 3 temas disponiveis você quer
aplicar. Depois pergunta qual o profile do terminal será aplicada as alterações.

Caso queira após a instalação inicial testar outros temas do solarized basta
executar o comando:
```
~/.cc_dotfiles/gnome-terminal-colors-solarized/install.sh
```

O último passo da instalação do cc_dotfiles irá pedir sua senha de usuário para
alterar seu shell padrão para o Zsh.


### Visão geral das configurações

Dentro do arquivo `~/.aliases` você vai encontrar vários atalhos para comandos
do sistema e de programas como Ruby e Git. São atalhos para tornar, algumas das
funções que você mais utiliza, mais simples e rápidas de se digitar.

O arquivo `~/.vim/settings/key_mappings.vim` tem as teclas de atalho mapeadas
para o uso do vim.

O arquivo `~/.vimrc` possui algumas das configurações que definem o
comportamento padrão do vim.

O arquivo `~/.vim/plugins.vim` possui a lista de plugins instalados no vim.

Existem outros arquivos de configurações para o tmux, zsh, git e vim. Eu
aconselho a com o tempo ir procurando entender o que cada arquivo, e cada
configuração faz aos programas. Assim você começa a ser capaz de realizar suas
próprias configurações, e assim pode ir montando seu próprio dotfiles.

No readme do projeto existem dois links para alguns dos atalhos do tmux e do
vim. Os demais atalhos e comandos podem ser encontrados nas docs dos programas e
plugins. E em alguns dos arquivos de configurações sitados acima.


### No pain no gain

Foi a frase que o Alan me disse quando falei que "Iria testar o dotfiles, mais
se acha-se muito complicado, voltaria ao meu antigo 'modus operandi' ". O começo
foi difícil de compreender como algumas coisas funcionavam. Mas com algum
esforço e estudo, agora começo a ver alguns frutos desse esforço.

Pretendo voltar num futuro próximo para falarmos mais sobre alguns truques
escondidos nos dotfiles da Campus, e em modos de você criar o seu próprio
dotfiles utilizando o cc_dotifiles como base.
