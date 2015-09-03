---
layout: post
title:  "Trabalhando com construtores e modificadores de classes em c# – Parte 1"
description: "Hoje irei abordar um assunto muito interessante que muitas vezes passa desapercebido e pode ser dor de cabeça mais dias ou menos dias.
Hoje irei falar sobre construtores e modificadores em c#, mesmo para desenvolvedores mais experientes esse pode ser um assunto ainda confuso quando falamos de assuntos além do comum, static, private, public."
date: 2015-09-02 21:39:06
categories: post 
dia: 02
mes: Setembro
ano: 2015
permalink: /trabalhando-com-construtores-e-modificadores-de-classes-c
image: "/assets/images/posts/c-construtores-e-modificadores.png"
leitura: 20 minutos
tags:
- c#
- construtores
lang: pt_BR
offtopic: false
ads: true
---

##Construtores de classes

Hoje irei abordar um assunto muito interessante que muitas vezes passa desapercebido e pode ser dor de cabeça mais dias ou menos dias.

Hoje irei falar sobre **construtores e modificadores em c#**, mesmo para desenvolvedores mais experientes esse pode ser um assunto ainda confuso quando falamos de assuntos além do comum, static, private, public.

Então vamos lá.

###1 – Construtores simples

{% highlight csharp %}
public class Semana
    {
        public DateTime Dia;

        public Semana()
        {
            Dia = DateTime.Now;
        }
    }

    class TestSemana
    {
        static void Main()
        {
            Semana semana = new Semana();
            Console.WriteLine(semana.Dia);
        }
    }
{% endhighlight %}

Neste exemplo vemos o uso simples de um **construtor**, sendo ele sem parâmetro, o construtor nesse caso será chamado toda vez que ocorrer um ‘new’ da classe, em nosso exemplo toda vez que ocorrer o ‘new’ o construtor irá setar a valor na variável Dia. Um construtor sem parâmetro é chamado de construtor Padrão.

Podemos trabalhar também com **múltiplos parâmetros** nos construtores de classes.

{% highlight csharp %}
public class Semana
    {
        public DateTime Dia;

        public Semana(int i)
        {
            Dia = DateTime.Now.AddDays(i);
        }

        public Semana(int i, int x)
        {
            Dia = DateTime.Now.AddDays(i).AddDays(x);
        }
    }

    class TestSemana
    {
        static void Main()
        {
            Semana semana1 = new Semana(1);
            Console.WriteLine(semana1.Dia);

            Semana semana2 = new Semana(1,2);
            Console.WriteLine(semana2.Dia);
        }
    }
{% endhighlight %}

Em nosso exemplo utilizamos diferentes construtores para definir a atribuição interna de nossa variável Dia.

*Não obrigatoriamente as classes devem ter um construtor sem parâmetro.*

###2 – Classes derivadas utilizando construtores de classes pai
`base` é utilizado para acessar os membros da classe base de dentro de uma classe derivada:
A classe base que é acessada é a classe base especificada na declaração da classe. Por exemplo, se você especificarclass ClassB : ClassA, os membros da ClassA são acessados da ClassB, independentemente da classe base da ClassA.

{% highlight csharp %}
public class Pessoa
    {
        protected string Cpf = "123.456.789-90";
        protected string Nome = "Valdir Viana";

        public virtual void ObterInfo()
        {
            Console.WriteLine("Nome: {0}", Nome);
            Console.WriteLine("Cpf: {0}", Cpf);
        }
    }

    class Funcionario : Pessoa
    {
        public string Id = "ABC345DEF";
        public override void ObterInfo()
        {
            // Neste ponto é chamdo o ObterInfo da classe Base(Pai)
            base.ObterInfo();
            Console.WriteLine("Funcionario Id: {0}", Id);
        }
    }

    class TestClass
    {
        static void Main()
        {
            Funcionario funcionario = new Funcionario();
            funcionario.ObterInfo();
        }
    }

    /*
    Saida
    Nome: Valdir Viana
    Cpf: 123.456.789-90
    Funcionario Id: ABC345DEF
    */
{% endhighlight %}

Neste exemplo criamos duas classes, uma chamada Pessoa com seu construtor e outra classe chamada funcionário que HERDA da classe Pessoa e também tem seu construtor com o mesmo nome.
Neste ponto você viu 2 coisas interessantes, que vou me aprofundar nos próximos posts sobre construtores e modificadores de classes.

**Virtual**: Mdificador que permite a classe ser alterada em classes derivadas.

**Override**: Modificador necessário para estender ou modificar a implementação de um método herdado.

O interessante ficou por conta do trecho `base.ObterInfo();` que é responsável por acessar o método na classe de herança da classe Funcionário. Porém neste exemplo anterior foi necessário a chamada no `base`, no próximo exemplo iremos implementar uma funcionalidade para ‘subentender’ a classe derivada sobre o construtor da classe pai.

Vejamos:

{% highlight csharp %}
public class ClassePai
    {
        int _num;

        public ClassePai()
        {
            Console.WriteLine("aqui ClassePai()");
        }

        public ClassePai(int i)
        {
            _num = i;
            Console.WriteLine("aqui ClassePai(int i)");
        }

        public int GetNum()
        {
            return _num;
        }
    }

    public class ClasseDerivada : ClassePai
    {
        // Este construtor chama ClassePai.ClassePai()
        public ClasseDerivada() : base()
        {
        }

        // Este construtor chama ClassePai.ClassePai(int i)
        public ClasseDerivada(int i) : base(i)
        {
        }

        static void Main()
        {
            ClasseDerivada cD = new ClasseDerivada();
            ClasseDerivada cD1 = new ClasseDerivada(1);
        }
    }
    /*
    Saida:
    aqui ClassePai()
    aqui ClassePai(int i)
    */
{% endhighlight %}

Neste exemplo anterior foi deixado assinado os **construtores das classes derivadas** que eles deveriam executar o construtor da classe pai também, utilizando o `base` como herança do construtor.

Agora você me pergunta, em que isso é **útil**. Em cenários de repositórios, onde você precisa instanciar alguma classe global, ou até algum tipo de IoC ou até mesmo conexão com db, você pode deixar essa responsabilidade somente com a classe pai, economizando chamada de código e tempo de processamento de classes com new.

Bom é isso galera, essa é a primeira parte, na segunda parte irei falar sobre, classe static, sealed, protected. Sabe a diferença? Então fica ligado ai.
Até a próxima.
