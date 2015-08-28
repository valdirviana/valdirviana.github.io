---
layout: post
title:  "Executando Jekyll no Windows - Parte 3"
description: "Se você estiver usando Markdown ou HTM, Jekyll torna mais fácil para você inserir belos blocos de código em suas páginas.Por padrão, Jekyll vem com o ‘highlights’ pygments.rb, que é um marcador de sintaxe baseado em Python. Para usá-lo no Windows, você precisará instalar o Python e algumas ferramentas extras."
date: 2015-08-28 00:23:06
categories: post 
dia: 28
mes: Agosto
ano: 2015
permalink: /executando-jekyll-windows-parte-2
image: "/assets/images/posts/jekyll-logo-light-solid.png"
leitura: 15-20 minutos
tags:
- jekyll
- windows
- python
lang: pt_BR
---

<p class="thumbnaill-post-70">
	<img src="{{ site.url }}/assets/images/posts/jekyll-logo-light-solid.png"/>
</p> 
	
####Ta chegando agora? Veja os anteriores:
[Executando Jekyll no Windows - Introdução]({{site.url}}/executando-jekyll-windows-introducao/)
<br/>
[Executando Jekyll no Windows - Parte 1]({{site.url}}/executando-jekyll-windows-parte-1/)
<br/>
[Executando Jekyll no Windows - Parte 2]({{site.url}}/executando-jekyll-windows-parte-2/)


##Visão Geral
Se você estiver usando [Markdown](http://daringfireball.net/projects/markdown/) ou HTM, Jekyll torna mais fácil
para você inserir belos blocos de código em suas páginas.

Por padrão, Jekyll vem com o 'highlights' pygments.rb, que é um marcador de sintaxe baseado em Python. Para usá-lo no Windows, 
você precisará instalar o Python e algumas ferramentas extras.

Uma boa alternativa é o Rouge baseado em Ruby, que é mais rápido e mais fácil de instalar, 
mas não suporta as mesmas línguas que pygments.

Abaixo, você encontrará instruções para ambos os marcadores de sintaxe. Escolha o que melhor se adapta às suas necessidades. 
Mais informações podem ser encontradas no [site oficial Jekyll](http://jekyllrb.com/docs/templates/#code-snippet-highlighting).

##Instalando Rougue
Rápido e simples: Abra o prompt de comando e digite o seguinte comando.
{% highlight console %}
gem install rouge
{% endhighlight %}

Então, abre o arquivo `_config.yml` (na raíz de seu projeto Jekyll), defina Rouge como seu marcador sintaxe:
{% highlight console %}
highlighter: rouge
{% endhighlight %}

Prontinho!

##Tornando Pygments Funcional
Se você quiser usar pygments, que é uma dependência padrão do Jekyll, para destaque de sintaxe no Windows, você precisará 
instalar Python, pip e a base de Python pygments.rb.

**Nota:** Depois de concluir as etapas a seguir, Jekyll pode ainda conter erros de saída na construção ou servindo sites. 
Estes não devem causar nenhum problema real embora, assim você pode ignorá-los com segurança.

##Instalando Python
A última versão do Python no momento é v2.7.10. Python 3 não vai funcionar.
Clique no [aqui](https://www.python.org/downloads/) para baixar o instalador **v2.7** que de acordo com arquitetura de seu sistema (x86 / x64).

Execute o arquivo baixado e siga os passos da instalação.

Quando você chegar à tela abaixo, certifique-se de clicar na caixa ao lado de "Add python.exe to Path".

<p class="thumbnaill-post-70">
	<img src="{{ site.url }}/assets/images/posts/python-path.png"/>
</p> 

##Instalando pip
Pip é uma ferramenta para instalação e gerenciamento de pacotes Python , semelhante ao Ruby Gems. Você vai precisar dele para instalar pygments, 
o pacote Python que pygments.rb usa para realçar seu código.

Primeiro, clique [aqui](https://pip.pypa.io/en/latest/installing.html) e baixe get-pip.py através do link no site.

**Nota:** O arquivo get-pip.py é um arquivo de texto comun com extensão do python, portando salve este arquivo em `c:/pip`

Agora abra o prompt de comando e vá até o local onde o arquivo esta.
{% highlight console %}
cd C:\pip
{% endhighlight %}

Em seguida, execute o seguinte comando para fazer o download e instalar automagicamente todos os componentes necessários.
{% highlight console %}
python get-pip.py
{% endhighlight %}

##Instalando a base do Python para Pygments
A partir do prompt de comando, execute o seguinte comando para instalar a base de Python pygments.
{% highlight console %}
python -m pip install Pygments
{% endhighlight %}

##Definir Pygments como seu marcador de sintaxe highlight
Se ainda não estiver definido, adicione o seguinte ao seu `_config.yml` para definir pygments como seu marcador de sintaxe.
{% highlight console %}
highlighter: pygments
{% endhighlight %}

##Resumo
Jekyll agora usará o marcador que você escolheu para fazer todos os seus blocos de código olhar super elegante. Estamos quase acabado.
Neste momento seu Jekyll já esta totalmente funcional, no próximo post iremos abordar algumas funções complementares do Jekyll.
Até a próxima.