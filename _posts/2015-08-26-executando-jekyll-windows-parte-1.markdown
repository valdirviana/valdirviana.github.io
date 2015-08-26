---
layout: post
title:  "Executando Jekyll no Windows - Parte 1"
description: "Então para prepararmos nosso ambiente para Jekyll devemos instalar o Ruby e o DevKit correspondente necessário para construir algumas dependências de Jekyll e algumas extensões nativas."
date:   2015-08-26 00:23:06
categories: post 
dia: 26
mes: Agosto
ano: 2015
permalink: /executando-jekyll-windows-parte-1
image: "/assets/images/posts/jekyll-logo-light-solid.png"
leitura: 10-15 minutos
tags:
- jekyll
- windows
- ruby
lang: pt_BR
---

<p class="thumbnaill-post-70">
	<img src="{{ site.url }}/assets/images/posts/jekyll-logo-light-solid.png"/>
</p> 
	
####Veja os anteriores:
[Executando Jekyll no Windows - Introdução]({{site.url}}/executando-jekyll-windows-introducao/)

##Instalando Ruby e Ruby DevKit

Como falado anteriormente na introdução desta série, Jekyll foi desenvolvido em Ruby. Então para prepararmos nosso ambiente para Jekyll
devemos instalar o Ruby e o DevKit correspondente necessário para construir algumas dependências de Jekyll e algumas extensões nativas.

##Instalando Ruby
Primeiramenta clique [aqui](http://rubyinstaller.org/downloads/) e faça o download da versão do Ruby de acordo com a arquitetura de seu sistema.

<p class="thumbnaill-post-50">
	<img src="{{ site.url }}/assets/images/posts/ruby-download-1.PNG"/>
</p> 

Execute a instalação. Quando o instalador chega a esta parte, como abaixo, certifique-se de marcar "Add Ruby executables to your PATH".
	
<p class="thumbnaill-post-50">
	<img src="{{ site.url }}/assets/images/posts/ruby-download-2.PNG"/>
</p> 

Finalize a instalação.

##Instalando o Ruby DevKit
Jekyll possuí algumas dependências, então precisamos instalar o DevKit para que toda execução ocorra como esperado.Para torná-los em executáveis ​​completamente funcionais, 
você provavelmente vai precisar instalar o DevKit em seu ambiente de desenvolvimento.

Clique [aqui](http://rubyinstaller.org/downloads/) e faça o download do DevKit de acordo com a versão que você escolheu no passo anterior
e de acordo com a arquitetura escolhida também x86 ou x64.

<p class="thumbnaill-post-50">
	<img src="{{ site.url }}/assets/images/posts/ruby-download-3.PNG"/>
</p> 

O download é um arquivo de auto-extração. Quando você executar o arquivo, ele irá pedir um destino para os arquivos. De preferência 
escolha o caminho `C:\RubyDevKit\`. Clique em extrair e espere até que o processo esteja concluído.

Em seguida, você precisa iniciar o DevKit e vinculá-lo à sua instalação Ruby. 
Abra o prompt de comando e navegue até a pasta que você extraiu o DevKit em: 
{% highlight console %}
cd C:\RubyDevKit
{% endhighlight %}
O próximo passo é detectar instalações de Ruby e adiciona-lo a um arquivo de configuração e vamos para a próxima etapa:
{% highlight console %}
ruby dk.rb init
{% endhighlight %}
Instale o DevKit , vinculando-o à sua instalação Ruby.
{% highlight console %}
ruby dk.rb install
{% endhighlight %}

##Resumo
É isso aí! Se tudo correu bem , agora você tem uma instalação do Ruby trabalhando em sua máquina e você 
pode construir executáveis ​​completamente funcionais usando o Ruby DevKit.
Caso queira instalar alguma Gem a mais é só executar a instalação a partir do prompt de comando.
No próximo passo iremos instalar a Gem do Jekyll.