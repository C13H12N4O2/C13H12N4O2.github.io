---
layout: post
title: "Class Exercise"
categories:
  - IT114
tags:
  - IT114
  - JAVA
last_modified_at: 2020-08-26-23-43
---

<strong>Class Exercise 1:</strong> Print messages

{% highlight java %}
public class PrintMessages {
  public static void main(String[] args) {
    System.out.println("University of Massachusetts Boston");
    System.out.println("100 Morrissey Boulevard");
    System.out.println("Boston, Massachusetts");
    System.out.println("02125-3393");
  }
}
{% endhighlight %}


<strong>Class Exercise 2:</strong> Solid box

{% highlight java %}
public class SolidBox {
  public static void main (String[] args) {
    drawLine();
    drawLine();
    drawLine();
  }

  public static void drawLine() {
    System.out.println("*****");
  }
}
{% endhighlight %}


<strong>Class Exercise 3:</strong> Data types and operators

{% highlight java %}
public class DataTypesAndOperators {
  public static void main(String[] args) {
    printIntegers();
    printDoubles();
    printChars();
    doCalculates();
  }

  public static void printIntegers() {
    System.out.println(55);
    System.out.println(-10);
  }

  public static void printDoubles() {
    System.out.println(3.14);
    System.out.println(-57.0);
  }

  public static void printChars() {
  System.out.println('c');
  System.out.println('s');
}

  public static void doCalculates() {
    int n1 = 4;
    int n2 = 5;
    int n3 = 6;

    System.out.println("n1 = " + n1);
    System.out.println("n2 = " + n2);
    System.out.println("n3 = " + n3);
    System.out.println("n1 + n2 = " + (n1 + n2));
    System.out.println("n3 + n1 = " + (n3 + n1));
    System.out.println("n1 * n3 = " + (n1 * n3));
    System.out.println("n3 / n1 = " + (n3 / n1));
    System.out.println("n3 % n1 = " + (n3 % n1));
    System.out.println("(n1 + n2) * n3 = " + (n1 + n2) * n3);
  }
}
{% endhighlight %}


<strong>Class Exercise 4:</strong> Expression Test

{% highlight java %}
public class ExpressionTest {
  public static void main(String[] args) {
    int a = 10;
    int b = 5;
    double d = 12.5;
    double c = 20.4;
    double e = b / a + (int)(d * c);
    
    System.out.println("The value of e is " + e);
    
    boolean flag1 = true;
    boolean flag2 = false;
    
    System.out.println(flag1);
    System.out.println(flag2);
    System.out.println("a<b?: " + (a < b));
    System.out.println("b/a==0?: " + (b / a == 0));
  }
}
{% endhighlight %}


<strong>Class Exercise 5:</strong> Print evens

{% highlight java %}
public class PrintEvens {
	public static void main(String[] args) {
		printEvens();
	}

	public static void printEvens() {
		for (int i = 1; i <= 25; i++) {
			System.out.println(i * 2);
		}
	}
}
{% endhighlight %}
