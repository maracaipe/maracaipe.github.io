---
layout: post
title: "Bower: O guia/tutorial  definitivo"
category: articles
description: Para quem sempre quis usar e não sabe como ou tem dificuldades em usar o Bower, aqui está o seu guia/tutorial definitivo!
tags: [bower, tutorial, dicas]
image:
  feature: /images/bower.png
comments: true
share: true
---

Antes de iniciar este post, gostaria de agradecer a todos pela repercursão que o [post anterior](www.carvalhoweb.com/articles/melhores-plugins-sublime-text/) teve. E como vocês são brothers, vão curtir, compartilhar e tweetar esse artigo aqui também.

Primeiramente, vamos falar o que o [Bower] é: Um **gerenciador de pacotes**, criado pelo pessoal do [Twitter](http://github.com/twitter), que serve principalmente para pacotes front-end. Caso você não saiba o que é um gerenciador de pacotes, é basicamente um arquivo (no caso do Bower, `bower.json`) em que você lista as dependências do seu projeto e os mantém atualizado com a fonte.

## Instalação

Para instalar o [Bower] globalmente, simplesmente no seu terminal bash execute `npm install -g bower`.  Ele é dependente do Node, Git (para a maioria dos pacotes) e do npm.

## Uso

Nesta seção, estarei listando os principais comandos do [Bower]. Para verificar se a instalação foi bem-sucedida, basta executar `bower -v` em qualquer lugar. Se for retornado algo, como na imagem, você já está pronto pra usar o bower.

![Bower -v](/images/guia-bower/bower-version.gif)

### Definindo depêndencias

Antes de instalar as dependências do seu projeto, você precisa primeiramente listá-las. Esta lista, nas versões superiores à `0.9.0` ficava armazenada no arquivo `components.json` e nas versões superiores, o aquivo é `bower.json`. Este arquivo precisa estar na raiz do seu projeto, e é semelhante a outros arquivos de outros gerenciadores como `package.json` do Node, ou `Gemfile` do Ruby.

Você pode iniciar um arquivo `bower.json` através do comando `bower init`, que pedirá que você especifique algumas opções. Após a criação bem sucedida desse arquivo, ele ficou assim:

<script src="https://gist.github.com/maracaipe/098bbdab68fd003dfee4.js"></script>

Pronto! Você já tem um arquivo `bower.json` válido e já podemos instalar as dependências.

### Instalando pacotes e dependências

O [Bower] oferece até hoje, quatro maneiras diferentes de se instalar pacotes. São elas:

##### Instala pacotes listados no arquivo `bower.json`

`bower install`

##### Instala pacote remoto ou local

`bower install <pacote>` 

##### Instala pacote remoto ou local em uma versão específica (indicada pela git tag)

`bower install <pacote>#<versao>` 

##### Instala pacote remoto ou local em uma versão específica (indicada pela git tag) com um nome diferente do pacote

`bower install <nome>=<pacote>#<versao>`

Nos exemplos acima, `<pacote>` pode ser o seguinte:

- O nome de um pacote registrado no Bower, por exemplo `jquery`
- Um repositório remoto, por exemplo `git://github.com/alguém/algum-pacote.git`
- Um repositório Git local
- Um atalho para um repositório no GitHub, por exemplo `alguem/algum-pacote`
- Uma URL para um arquivo `.zip` ou `.tar.gz`

Usando o jeito mais simples, instalei o [jQuery](//github.com/jquery/jquery) (`bower install jquery --save`) como exemplo. Os arquivos do jQuery, ficam armazenados em `/bower_components/jquery`. E se você quiser usar por exemplo o arquivo `jquery.min.js`, é só apontar para a pasta em que o componente foi adicionado.

Se você quiser instalar algum pacote e já listá-lo no arquivo `bower.json` é só colocar a opção `-D` ou `--save`, deixando o comando assim: `bower install <pacote> --save`. Caso o pacote seja um dependência somente no estágio de desenvolvimento, a opção `--save-dev` ou `-D` o lista nas `devDependencies` no arquivo json.

Por padrão, todos os pacotes são instalados no diretório `bower_components` e você não deve modificar seu conteúdo. Adicione-a ao seu .gitignore para nas próximas utilizações, a pessoa somente executar `bower install` e o bower adicionar todos os componentes. Para listar todos os pacotes instalados localmente, execute `bower list`.

### Adicionando dependências

Nesta seção, você vai adicionar as dependências ao seu arquivo `bower.json` e com isso, cada vez que você executa `bower install` para instalar os pacotes na primeira vez, ou `bower update` para atualizar os já existentes. O seguinte arquivo `bower.json` mostra como deve ser listado as dependências, e toma como exemplo os pacotes **Bootstrap** e **jQuery** (ambos na última versão).

<script src="https://gist.github.com/maracaipe/3feb2d571cdb9867972b.js"></script>

### Desinstalando pacotes e excluindo dependências

Caso você não precise de mais algum pacote e deseja excluir sua dependência, é só executar `bower uninstall <pacote>` e retirá-lo das dependências no arquivo json ou, se quiser já retirá-lo das dependências no arquivo json automaticamente, execute `bower uninstall <pacote> --save`.

### Listando pacotes instalados

Para ver quais pacotes estão instalados no seu projeto, simplesmente execute `bower list`. Para ver também o caminho desses pacote, adicione ao comando a opção `--paths`.

### Alterar diretório padrão

Se você não quiser que o [Bower] coloque tudo (como padrão) no diretório `bower_components`, você pode instalar em outro lugar, adicionando um arquivo chamado `.bowerrc` na raiz do projeto. Para mudar o diretório para `assets/components` nosso arquivo vai ficar assim:

<script src="https://gist.github.com/maracaipe/6bcb60178110531025ac.js"></script>

Depois é só executar `bower install` novamente e deletar o diretório anterior.

### Utilizando um pacote

Essa parte provavelmente você já sabe, mas mesmo assim vou deixá-la aqui. Supondo que você tem somente o jQuery como pacote e vai utilizá-lo como nos exemplos anteriores, você vai usar na sua página assim:

<script src="https://gist.github.com/maracaipe/b4ed6c626bf2428357e7.js"></script>

-------

Pronto! Você já sabe usar o bower e utilizá-lo em seus projetos. Se você gostou e é um brother, não esqueça de curtir, compartilhar, tweetar a dar um +1 neste post. Qualquer dúvida ou observação, é só colocar nos comentários logo abaixo. Aproveitando, se você ainda não viu o post sobre [Os Melhores Plugins do Sublime Text](www.carvalhoweb.com/articles/melhores-plugins-sublime-text/) dê uma passada lá e veja! Até mais!

[Bower]: http://bower.io/