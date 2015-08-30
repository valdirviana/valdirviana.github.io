---
layout: post
title:  "Executando Jekyll no Windows - Final"
description: "Jekyll tem um recurso de auto-reconstrução interna que observa seus arquivos de origem e reconstrói seu site. Executando Jekyll, execute o comando a seguir."
date: 2015-08-29 19:39:06
categories: post 
dia: 29
mes: Agosto
ano: 2015
permalink: /executando-jekyll-windows-parte-final
image: "/assets/images/posts/jekyll-logo-light-solid.png"
leitura: 10 minutos
tags:
- jekyll
- windows
lang: pt_BR
offtopic: false
---
	
####Ta chegando agora? Veja os anteriores:
[Executando Jekyll no Windows - Introdução]({{site.url}}/executando-jekyll-windows-introducao/){:target="_blank"}
<br/>
[Executando Jekyll no Windows - Parte 1]({{site.url}}/executando-jekyll-windows-parte-1/){:target="_blank"}
<br/>
[Executando Jekyll no Windows - Parte 2]({{site.url}}/executando-jekyll-windows-parte-2/){:target="_blank"}
<br/>
[Executando Jekyll no Windows - Parte 3]({{site.url}}/executando-jekyll-windows-parte-3/){:target="_blank"}


##Usando Jekyll --watch
Jekyll tem um recurso de auto-reconstrução interna que observa seus arquivos de origem e reconstrói seu site.
Executando Jekyll, execute o comando a seguir.
{% highlight console %}
jekyll new myblog
cd myblog
jekyll serve

Now browse to http://localhost:4000
{% endhighlight %}

Em Jekyll você hospeda sua página em `http://localhost:4000`.

Ou você pode utilizar:
{% highlight console %}
jekyll build --watch
{% endhighlight %}

##Instalando wdm Gem
No Windows, você precisará instalar uma ferramenta adicional, ou melhor, uma Gem, para habilitar essa funcionalidade. 
Simplesmente execute o seguinte comando a partir da linha de comando.
{% highlight console %}
gem install wdm
{% endhighlight %}

##Finalmente Fim
Você aprendeu nessa pequena série como preparar o ambiente para desenvolver Jekyll em um ambiente Windows.
Abaixo deixo alguns links úteis para te auxiliar no desenvolvimento de páginas com Jekyll:

[Jekyll on Windows](http://jekyll-windows.juthilo.com/){:target="_blank"} -> Série base para meus posts
<br/>
[Jekyll](http://jekyllrb.com/){:target="_blank"} -> Site do Jekyll
<br/>
[Markdown-Guide](http://markdown-guide.readthedocs.org/en/latest/basics.html){:target="_blank"} -> Um guia para utilizar markdown na escrita de sua páginas/posts
<br/>
[Pygment Highlighter](http://pygments.org/languages/){:target="_blank"} -> Linguagem que você pode escrever com Pygments
<br/>
[Html5 Up](http://html5up.net/){:target="_blank"} -> Alguns temas gratuitos constrstuídos em Html5 para você usar.

E ai pessoal, curtiram essa primeira série? Espero que sim, se puder deixar sua breve opinião nos comentários abaixo ou até mesmo compartilhar em suas redes sociais.

Um grande abraço.