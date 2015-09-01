---
layout: post
title:  "Usando run em módulos AngularJS"
description: "Boas galera, hoje vou falar um pouco sobre AngularJS, irei abordar um pequeno assunto mas que me ajudou a solucionar um grande 
problema em uma estrutura de um projeto que trabalhei recentemente. Para quem esta acostumado com C#, o run de módulos AngularJS é meio que **similar** ao global.asax, ou seja, um trecho de código
que será executado anterior aos processos iniciais da página."
date: 2015-08-31 22:39:06
categories: post 
dia: 31
mes: Agosto
ano: 2015
permalink: /usando-init-em-modulos-angularjs
image: "/assets/images/posts/angularjslogo2background.png"
leitura: 10 minutos
tags:
- javascript
- angularjs
lang: pt_BR
offtopic: false
ads: true
---


##Init - AngularJS
Boas galera, hoje vou falar um pouco sobre AngularJS, irei abordar um pequeno assunto mas que me ajudou a solucionar um grande 
problema em uma estrutura de um projeto que trabalhei recentemente.

Para quem esta acostumado com C#, o run de módulos AngularJS é meio que **similar** ao global.asax, ou seja, um trecho de código
que será executado anterior aos processos iniciais da página.

###Como fazer

Ao contrário dos blocos de configuração, o método **run** é executado após o injetor, é criado e executado em primeiro em qualquer lugar do app AngularJS.

O run é o que está mais próximo do core de execução do Angular no inicio da aplicação.

Normalmente o run e usado para definir algumas funções globais ao app, predefinir configurações, criar listener de eventos e até
verificar autenticação.

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

Vamos pensar em uma aplicação em que a rota é desviada constantemente dentro do app e você precise verificar sempre a autenticação 
do usuário. Então este é o lugar.


{% highlight js %}
angular.module('myApp', ['ngRoute'])
.run(function($rootScope, AuthService) { $rootScope.$on('$routeChangeStart',
  function(evt, next, current) {
    // Verifica se o usuário esta logado
    if (!AuthService.userLoggedIn()) {
      if (next.templateUrl === "login.html") {
        // Caso não esteja, é redirecionado
      } else {
        $location.path('/login');
		}
	}
	});
});
{% endhighlight %}

O bloco acima irá se comportar da seguinte maneira, sempre que ocorrer a chamada de uma nova rota, o run irá ser executado antes
dos controllers.

E ai pessoal o que acharam ? Sugestões? Xingamentos? Deixa seu comentário por favor.

Inté maisss...