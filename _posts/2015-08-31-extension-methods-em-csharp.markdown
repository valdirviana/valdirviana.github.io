---
layout: post
title:  "Extension Methods em C#"
description: "Boas galera, hoje vamos aprender a criar extensions methods para auxiliar no desenvolvimento com C#. Extensions Methods são muito úteis quando você precisa de uma rotina que vá ser chamada constantemente em seu código, extension methods permite que você adicione métodos a tipos primitivos e existentes, sem a necessidade de criar um novo tipo derivado. Alguns extensions méthods já estão implementados no frameworks veja alguns para string."
date: 2015-08-31 10:39:06
categories: post 
dia: 31
mes: Agosto
ano: 2015
permalink: /extension-methods-em-csharp
image: "/assets/images/posts/c-extension.png"
leitura: 15 minutos
tags:
- c#
- extension method
lang: pt_BR
offtopic: false
---

##Criando Extensions Methods em C#
Boas galera, hoje vamos aprender a criar extensions methods para auxiliar no desenvolvimento com C#.

Extensions Methods são muito úteis quando você precisa de uma rotina que vá ser chamada constantemente em seu código, **extension methods** permite que você adicione métodos a tipos primitivos e existentes, sem a necessidade de criar um novo tipo derivado.

Alguns extensions méthods já estão implementados no frameworks veja alguns para string.
{% highlight csharp %}
string s;
var x = s.toLower();
var x = s.trim();
{% endhighlight %}

Com extension methods você pode fazer algo como:
{% highlight csharp %}
string s;
var x = s.MaisculaNaPrimeiraLetra();
{% endhighlight %}


###Método MaisculaNaPrimeiraLetra()
No exemplo a baixo criei um método que recebe uma string e retorna a mesma string porém com a primeira letra da cadeia de 
caracteres maiuscula.
{% highlight csharp %}
using System;
class Program
{
    static void Main()
    {
		Console.WriteLine(MaisculaNaPrimeiraLetra("valdir precisa escrever melhor"));
    }
    static string MaisculaNaPrimeiraLetra(string s)
    {
	// Verifica se a string é nula ou vazia
	if (string.IsNullOrEmpty(s))
	{
	    return string.Empty;
	}
	// Retorna a mesma string porém com o primeiro caracter maiusculo
	return char.ToUpper(s[0]) + s.Substring(1);
    }
}
{% endhighlight %}

###Método MaisculaNaPrimeiraLetra() usando Extension Method
Embora o método acima funcione bem, image a situação em que você precise de algo mais complexo.
{% highlight csharp %}
string text =  "valdir precisa escrever melhor";
text = text.MaisculaNaPrimeiraLetra();
{% endhighlight %}
Ou você pode utilizar dessa forma
{% highlight csharp %}
string text = "valdir precisa escrever melhor".MaisculaNaPrimeiraLetra();
{% endhighlight %}

Bom, para poder utilizar a segunda forma, você precisa criar o extension method para o tipo **string**. Veja como:
{% highlight csharp %}
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace StringExtensionMethods
{
    //Extension methods deve ser declarada como static
    public static class StringExtension
    {       
        public static string MaisculaNaPrimeiraLetra(this string s)
        {
            // Verifica se a string é nula ou vazia.
            if (string.IsNullOrEmpty(s))
            {
                return string.Empty;
            }

            // Retorna a mesma string porém com o primeiro caracter maiusculo
            return char.ToUpper(s[0]) + s.Substring(1);

        }
    }
}
{% endhighlight %}
Agora podemos chama-lo usando.
{% highlight csharp %}
using StringExtensionMethods;

namespace Samples
{
    class Program
    {      
        static void Main(string[] args)
        {  
            string text = "valdir precisa escrever melhor".MaisculaNaPrimeiraLetra();
        }
    }
}
{% endhighlight %}	

E ai curtiu esse post? Deixe seu comentário e opinião, isso é muito importante para nós.

Grande abraço.