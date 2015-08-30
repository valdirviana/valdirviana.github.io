---
layout: post
title:  "Executando Jekyll no Windows - Introdução"
description: "Jekyll é um simples porém muito útil gerador de conteúdo estático para sites e até blogs, em ambientes Mac OS X e Linux a configuração é uma tarefa trivial,
porém no Windows nen tanto. Este pequeno tutorial dívido em 4 partes irá te auxiliar a montar um ambiente de desenvolvimento em sua máquina Windows."
date:   2015-08-25 11:23:06
categories: post 
dia: 25
mes: Agosto
ano: 2015
permalink: /executando-jekyll-windows-introducao
image: "/assets/images/posts/jekyll-logo-light-solid-trianglify.png"
leitura: 7 minutos
tags:
- jekyll
- windows
lang: pt_BR
offtopic: false
---


##Introdução

[Jekyll](http://jekyllrb.com/){:target="_blank"} é um simples porém muito útil gerador de conteúdo estático para sites e até blogs, em ambientes Mac OS X e Linux a configuração é uma tarefa trivial,
porém no Windows nen tanto. Este pequeno tutorial dívido em 5 partes irá te auxiliar a montar um ambiente de desenvolvimento em sua máquina Windows.

Jekkyl é uma gem portando executa em cima da plataforma do [Ruby](https://www.ruby-lang.org/pt/){:target="_blank"}.

Atenção: Note que o uso de Jekyll no Windows não é oficialmente suportado pela equipe do Jekyll. Enquanto esta guia existir, o Jekyll para Windows permanece 
não oficial.

> Enquanto o Windows não é uma plataforma oficialmente suportada, ele pode ser usado para realizar alguns ajustes adequados com Jekyll. Esta página tem como
objetivo fornecer alguns conhecimentos que foram desenterrados por usuário Windows.
[Documentação do Jekyll para Windows](http://jekyllrb.com/docs/windows/){:target="_blank"}

<script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
<!-- valdirviana.github.io - Intro post (so texto) -->
<ins class="adsbygoogle"
     style="display:block"
     data-ad-client="ca-pub-7851524114238986"
     data-ad-slot="3633647753"
     data-ad-format="auto"></ins>
<script>
(adsbygoogle = window.adsbygoogle || []).push({});
</script>

##Versões
Ao termino desse tutorial você irá ter as seguintes versões de softwares. Estes foram testados de forma funcional para trabalhar com Jekyll no Windows.

As versões que tem sido testadas com sucesso estão listadas abaixo. É recomendado manter suas Gems atualizados até as versões abaixo.

**Softwares**

| Software (package)| Versão | Testado até |
| ------------- |:-------------: | -----: |
| Ruby | 2.0.0p576 | 2.0.0p481 |
| Jekkyl | 2.5.1 |  2.4.0 2.3.0 2.2.0 2.1.1 2.1.0 |
| listen | 2.7.11 | ND |
| wdm | 0.1.0 | ND |

***
<br/>

**Caso use a sintaxe Pygments**(Iremos abordar nesse tutorial)

| Software (package) | Versão |Testado até |
| ------------- |:-------------: | -----:|
| pygments.rb | 0.6.0 | ND |
| Python | 2.7.8 | ND |
| pip | 1.5.6 | ND |
| setuptools | 5.4.1 | ND |
| Pygments | 1.6 | ND |

***

<br/>

##Jekkyl Portable
Existe uma versão portátil do Jekkyl criado por [@madhur](https://github.com/madhur){:target="_blank"}, porém não iremos abordar nesse tutorial esta ferramenta. Caso queira ver clique [aqui](https://github.com/madhur/PortableJekyll).

