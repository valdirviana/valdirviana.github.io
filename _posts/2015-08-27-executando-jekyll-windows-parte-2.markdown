---
layout: post
title:  "Executando Jekyll no Windows - Parte 2"
description: "Assim como abordamos nos posts anteriores, Jekyll é fornecido através de uma Gem do Ruby, o que o torna muito fácil de se instalar. Para instalar Jekyll e todas as suas dependências padrão, utilize o prompt de comando e digite o comando a seguir."
date:   2015-08-27 10:23:06
categories: post 
dia: 27
mes: Agosto
ano: 2015
permalink: /executando-jekyll-windows-parte-2
image: "/assets/images/posts/jekyll-logo-light-solid.png"
leitura: 10 minutos
tags:
- jekyll
- windows
lang: pt_BR
---

<p class="thumbnaill-post-70">
	<img src="{{ site.url }}/assets/images/posts/jekyll-logo-light-solid.png"/>
</p> 
	
####Veja os anteriores:
[Executando Jekyll no Windows - Introdução]({{site.url}}/executando-jekyll-windows-introducao/)
[Executando Jekyll no Windows - Parte 1]({{site.url}}/executando-jekyll-windows-parte-1/)

##Instalação
Assim como abordamos nos posts anteriores, Jekyll é fornecido através de uma Gem do Ruby, o que o torna muito fácil de se instalar.
Para instalar Jekyll e todas as suas dependências padrão, utilize o prompt de comando e digite o comando a seguir.
{% highlight console %}
gem install jekyll
{% endhighlight %}
Aperte o enter e espere o gerenciador instalar Jekyll e todas as suas dependências, isso pode levar algum tempo.

##Compatibilidade
A versão atual e estável do Jekyll é a 2.5.3 que é compatível com Windows. A maioria das versões anteriores também são compatíveis,
mas não instale a versão 1.4.3 que é conhecida por não ser compatível com Windows.

##Resumo
Nessa etapa você já instalou com sucesso o Jekyll. Nesse momento já é possível construir e servir sites estáticos com sucesso e sem erros,
a menos que haja sintaxe de 'highlights'. Para saber como configurar corretamento os processadores de sintaxe de 'highlight' acompanhe o
próximo post. Até a próxima.