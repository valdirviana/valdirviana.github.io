---
layout: post
title:  "If-Else ou (?:) – Qual Operador (Ternário) condicional tem melhor performance"
description: "Boas galera, hoje irei falar sobre operador (ternário) condicional. Você sabe como utilizar? Sabe como e onde usa-lo e qual quer melhor performance.A palavra ternário significa: Formado por três partes Então nossos operadores condicionais são compostos por três partes, da seguinte forma:"
date: 2015-09-05 21:39:06
categories: post 
dia: 05
mes: Setembro
ano: 2015
permalink: /trabalhando-com-construtores-e-modificadores-de-classes-c
image: "/assets/images/posts/c-operador-ternario.png"
leitura: 10 minutos
tags:
- c#
lang: pt_BR
offtopic: false
ads: true
---

Boas galera, hoje irei falar sobre operador (ternário) condicional. Você sabe como utilizar? Sabe como e onde usa-lo e qual quer melhor performance.
A palavra **ternário** significa: Formado por três partes
Então nossos operadores condicionais são compostos por três partes, da seguinte forma:

{% highlight text %}
IF(CONDICAO)
{	
         EXPRESSAO 1 – SE CONDICAO VERDADEIRA
}
ELSE
{
	EXPRESSAO 2 – SE CONDICAO FALSA
}
{% endhighlight %}

ou

{% highlight text %}
CONDICAO ? EXPRESSAO 1 SE CONDICAO VERDADEIRA : EXPRESSAO 2 SE CONDICAO FALSE
{% endhighlight %}

Sempre irá ocorrer desta forma, mesmo que a EXPRESSA 2 seja não fazer algo, mas ela existe.
E como funciona na prática, qual é mais performático?
Vamos fazer um pequeno teste:

{% highlight csharp %}
Stopwatch s = new Stopwatch();

int test = 0;
s.Start();
		
//Exemplo 1
for (int a = 0; a < 100000000; a++)
{
     test = a % 50 == 0 ? 1 : 2;
}
s.Stop();
//Segundos = 0.9254454

s.Restart();
//Exemplo 2
for (int b = 0; b < 100000000; b++)
{
   if (b % 50 == 0)
        test = 1;
   else
        test = 2;
}
s.Stop();
//Segundos =  0.8018984
{% endhighlight %}

Em nosso teste o exemplo 2 foi mais performático que o exemplo 1, então qual a vantagem de se usar um e outro.

**Exemplos 1:**
Neste caso, usar esse tipo de condição é mais viável em situações onde a condição verdadeira e falsa irá demandar uma grande quantidade de trecho de código.

**Exemplo 2:** 
Neste caso, o uso é melhor quando sua expressão e a condição verdadeira e false vai demandar pouco quantidade de código limitada a 1 linha.

Muito obrigado galerinha, até a próxima.
