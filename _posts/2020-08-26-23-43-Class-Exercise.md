---
layout: post
title: "Class Exercise"
categories:
  - IT114
tags:
  - IT114
  - JAVA
last_modified_at: 2020-08-27-23-47
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


<strong>Class Exercise 6:</strong> Hours in day 2

{% highlight java %}
public class HoursInDay2 {
  public static final int HALF_A_DAY = 12;

  public static void main (String[] args) {
    System.out.println("Hours in the day");
    printHours("AM");
    System.out.println();
    printHours("PM");
  }
  
  public static void printHours(String dayPart) {
    for (int hour = 1; hour <= HALF_A_DAY; hour++) {
      System.out.println(hour + " " + dayPart);
    }
  }
}
{% endhighlight %}


<strong>Class Exercise 7:</strong> Show interest

{% highlight java %}
public class ShowInterest {
  public static void main (String[] args) {
    double balance = 1000;
    System.out.println("The balance is " + balance);
    balance += interest(balance);
    System.out.println("The balance is now " + balance);
    System.out.println("Now the balance is " + (balance + interest(balance, 6)));
  }

  public static double interest(double value) {
    return value * .05;
  }

  public static double interest(double value, int percent) {
    return value * percent / 100;
  }
}
{% endhighlight %}


<strong>Class Exercise 8:</strong> Math Experiment

{% highlight java %}
public class MathExperiment {
  public static void main(String[] args) {
    System.out.println("2^3 is: " + Math.pow(2, 3));
    System.out.println("The square root of 25 is: " + Math.sqrt(25));
    System.out.println("The absolute avlue of -12 is: " + Math.abs(-12));
    System.out.println("The max of -1 and 1 is: " + Math.max(-1, 1));
    
    int a = -1, b = 0;
    System.out.println("The larger og (" + a + ", " + b + ") is: " + getLarger(a, b));
    
    int result1 = (int)(Math.random() * 6 + 1);
    System.out.println("The random number generated is: " + result1);
    
    System.out.println("The distance is: " + getDistance(1, 0, 4, 4));
  }
  
  public static double getDistance(double x1, double y1, double x2, double y2) {
    return Math.sqrt(Math.pow(x2 - x1, 2) + Math.pow(y2 - y1, 2));
  }

  public static int getLarger(int a, int b) {
    if (a > b) 
      return a;
    else 
      return b;
  }
}
{% endhighlight %}


<strong>Class Exercise 9:</strong> String Experiment

{% highlight java %}
public class StringExperiment {
  public static void main(String[] args) {
    String first = "Hello";
    String second = "world";
    String newString = first + " " + second + "!";
    System.out.println("newString: " + newString);
    System.out.println("The length of newString is: " + newString.length());
    System.out.println("The first character in newString is " + newString.charAt(0));
    System.out.println("The last character in newString is " + newString.charAt(newString.length() -1));
    System.out.println("The first word in newString is " + newString.substring(0, 5));
    System.out.println(newString.toLowerCase());
    System.out.println(newString.toUpperCase());
    
    String s = "A Tale of two Cities";
    System.out.println("Original string is: " + s);
    System.out.println("The reversed string is: " + getReverse(s));
  }
  
  public static String getReverse(String s) {
    String newS = "";

    for (int i = s.length() -1; i >= 0; i--) 
      newS += s.charAt(i);

      return newS;
  }
}
{% endhighlight %}


<strong>Class Exercise 10:</strong> Positive negative and string

{% highlight java %}
import java.util.*;

public class PositiveNegativeAndString {
  public static void main(String[] args) {
    Scanner input = new Scanner(System.in);
    
    System.out.print("Please enter an integer: ");
    
    int number = input.nextInt();
    String description = positiveNegative(number);
    System.out.println(number + " is " + description);
    System.out.println();
    
    String s1 = "Hello";
    String s2 = "hello";
    String s3 = "HELLO";
    String s4 = "Hello";
    
    System.out.println("S1 is squal to S2?: " + s1.equals(s2));
    System.out.println("S1 is squal to S3?: " + s1.equals(s3));
    System.out.println("S1 is squal to S4?: " + s1.equals(s4));
    System.out.println("S2 is squal to S3?: " + s2.equals(s3));
  }
  
  public static String positiveNegative(int num) {
    String result = "";
    
    if (num > 0)
      result = "positive";
    else if (num < 0)
      result = "negative";
    else
      result = "zero";
      
    return result;
  }
}
{% endhighlight %}


<strong>Class Exercise 11:</strong> Mortgage

{% highlight java %}
import java.util.Scanner;

public class Mortgage {
  public static void main(String[] args) {
    Scanner console = new Scanner(System.in);
    
    System.out.println("This program computes mmonthly mortgage payments.");
    
    System.out.print("The client's name of this loan: ");
    String name = console.nextLine();
    
    System.out.print("Loan amount: ");
    double loan = console.nextDouble();
    
    System.out.print("Number of years: ");
    int years = console.nextInt();
    
    System.out.print("Interest rate: ");
    double rate = console.nextDouble();	
    System.out.println();
    
    int months = 12 * years;
    double c = rate / 12.0 / 100.0;
    double payment = loan * c * Math.pow(1 + c, months) / (Math.pow(1 + c, months) - 1);
    
    System.out.println("For Client " + name + " the payment = $" + (int) payment);
  }
}
{% endhighlight %}


<strong>Class Exercise 12:</strong> Average

{% highlight java %}
import java.util.*;

public class Average {
  public static void main(String[] args) {
    Scanner console = new Scanner(System.in);
    System.out.print("How many numbers do you have? ");
    int numberOfNumbers = console.nextInt();
    
    double sum = 0.0;
    
    for (int i = 1; i <= numberOfNumbers; i++) {
      System.out.print("     #" + i + " ? ");
      double next = console.nextDouble();
      sum += next;
    }
    
    if (numberOfNumbers <= 0) {
      System.out.println("No numbers to average");
    } else {
      double average = sum / numberOfNumbers;
      System.out.println("average: " + average);
    }
  }
}
{% endhighlight %}


<strong>Class Exercise 13:</strong> Minimum

{% highlight java %}
import java.util.*;

public class Minimum {
  public static void main(String[] args) {
    Scanner input = new Scanner(System.in);
    System.out.print("How many integers will you enter: ");
    int number = input.nextInt();
    int minimum = findMin(input, number);
    
    System.out.println(minimum + " is the minimum number you entered.");
  }
  
  public static int findMin(Scanner input, int num) {
    int min = Integer.MAX_VALUE;
    
    for (int i = 1; i <= num; i++) {
      System.out.print("Please enter an integer: ");
      
      int value = input.nextInt();
      
      if (value < min) 
        min = value;
    }

    return min;
  }
}
{% endhighlight %}


<strong>Class Exercise 14:</strong> Smallest divisor

{% highlight java %}
import java.util.Scanner;

public class SmallestDivisor {
  public static void main(String[] args) {
    Scanner input = new Scanner(System.in);
    
    System.out.print("Please enter a number: ");
    int num = input.nextInt();
    
    System.out.println("The smallest divisor for this number is: " + smallestDivisor(num));
  }
  
  public static int smallestDivisor(int num) {
    int divisor = 2;
    
    while (num % divisor != 0)
      divisor++;
      
    return divisor;
  }
}
{% endhighlight %}


<strong>Class Exercise 15:</strong> Loop test

{% highlight java %}
import java.util.*;

public class LoopTest {
  public static void main(String[] args) {
    doWhileTest();
    System.out.println();
    getAge();
  }
  
  public static void doWhileTest() {
    int sum = 0;
    Random rand = new Random();
    
    do {
      int die1 = rand.nextInt(6) + 1;
      int die2 = rand.nextInt(6) + 1;
      
      sum = die1 + die2;
      
      System.out.println(die1 + " + " + die2 + " = " + sum);
    } while (sum != 7);
  }
  
  public static void getAge() {
    Scanner console = new Scanner(System.in);
    int age = getInt(console, "How old are you?");
    
    System.out.println("You have told me your age is: " + age);
  }
  
  public static int getInt(Scanner console, String prompt) {
    System.out.println(prompt);
    
    while (!console.hasNextInt()) {
      console.next();
      
      System.out.println("Not an integer; try again.");
      System.out.println(prompt);
    }

    return console.nextInt();
  }
}
{% endhighlight %}


<strong>Class Exercise 16:</strong> Count letters

{% highlight java %}
import java.util.Scanner;

public class CountLetters {
  public static void main(String[] args) {
    Scanner input = new Scanner(System.in);
    System.out.print("Pleae enter a string: ");
    String s = input.nextLine();
    System.out.println("Counted " + countAlphabetLetters(s) + " alphabetical letters.");
    System.out.println("Counted " + countDigitalLetters(s) + " digital letters.");
    System.out.println("Counted " + countUppercaseLetters(s) + " letters in uppercase.");
  }
  
  public static int countAlphabetLetters(String s) {
    int count = 0;
    
    for (int i = 0; i < s.length(); i++) {
      if (Character.isLetter(s.charAt(i))) 
        count++;
    }
    
    return count;
  }
  
  public static int countDigitalLetters(String s) {
    int count = 0;
    
    for (int i = 0; i < s.length(); i++) {
      if (Character.isDigit(s.charAt(i)))
        count++;
    }
    
    return count;
  }
  
  public static int countUppercaseLetters(String s) {
    int count = 0;
    
    for (int i = 0; i < s.length(); i++) {
      if (Character.isUpperCase(s.charAt(i)))
        count++;
    }
    
    return count;
  }
}
{% endhighlight %}


<strong>Class Exercise 17:</strong> Recursion practice

{% highlight java %}
import java.util.*;

public class RecursionPractice {
  public static void main(String[] args) {
    Scanner input = new Scanner(System.in);
    
    System.out.println("Computing Factorial.");
    System.out.print("Please enter a number: ");
    
    int num = input.nextInt();
    
    if (num < 0) 
      System.out.println("There is no factorial for a negative number.");
    else 
      System.out.println(factorial(num));
      
    System.out.println();
    
    System.out.println("Computing Greatest Common Divisor.");
    System.out.println("Please enter two nummbers: ");
    
    int num1 = input.nextInt();
    int num2 = input.nextInt();
    
    if (num1 == 0 && num2 == 0)
      System.out.println("No greatest commmon divisor.");
    else 
      System.out.println("The greatest commmon divisor of these two numbers is: " + gcd(num1, num2));
  }
  
  public static int factorial(int num) {
    if (num == 0)
      return 1;
    else
      return num * factorial(num - 1);
  }
  
  public static int gcd(int a, int b) {
    if (a == 0) 
      return b;
    else {
      if (b == 0)
        return a;
      else 
        return gcd(b, a % b);
    }
  }
}
{% endhighlight %}


<strong>Class Exercise 18:</strong> Try catch

{% highlight java %}
import java.io.*;
import java.util.Scanner;

public class TryCatch {
  public static void main(String[] args) {
    try {
      readFile();
    } catch (FileNotFoundException e) {
      System.out.println("Not such a file.");
    }
  }
  
  public static void readFile() throws FileNotFoundException {
    String filename = "foo.txt";
    Scanner input = new Scanner(new File(filename));
    
    System.out.println("Created Scanner object on " + filename);
  }
}
{% endhighlight %}


<strong>Class Exercise 19:</strong> Show sum prompt for file

{% highlight java %}
import java.util.*;
import java.io.*;

public class ShowSumPromptForFile {
  public static void main(String[] args) {
    try {
      System.out.println("Will add a serires of numbers from a file.");
      System.out.println();
      
      Scanner console = new Scanner(System.in);
      System.out.println("What is the file's name?");
      String name = console.nextLine();
      Scanner input = new Scanner(new File(name));
      System.out.println();
      
      double sum = 0;
      int count = 0;
      
      while (input.hasNextDouble()) {
        double next = input.nextDouble();
	count++;
	
	System.out.println("number " + count + " = " + next);
	sum += next;
      }
      
      System.out.println("The sum is: " + sum);
    }
    
    catch (FileNotFoundException e) {
      System.out.println("The file does not exist.");
    }
  }
}
{% endhighlight %}


<strong>Class Exercise 20:</strong> Hours worked with ID

{% highlight java %}
import java.io.*;
import java.util.*;

public class HoursWorkedWithID {
  public static void main(String[] args) {
    try {
      Scanner input = new Scanner(new File("id_hours.txt"));
      
      while (input.hasNextLine()) {
        String line = input.nextLine();
	processLine(line);
      }
    } catch (FileNotFoundException e) {
      System.out.println("The file does not exist");
    }
  }
  
  public static void processLine(String line) {
    Scanner data = new Scanner(line);
    int id = data.nextInt();
    String name = data.next();
    double sum = 0;
    
    while (data.hasNextDouble())
      sum += data.nextDouble();
      
    System.out.println("Total hours worked by " + name + "(ID#" + id + ")= " + sum);
  }
}
{% endhighlight %}


<strong>Class Exercise 21:</strong> Average temperature

{% highlight java %}
import java.util.*;

public class AverageTemperature {
  public static void main(String[] args) {
    Scanner console = new Scanner(System.in);
    int[] temps = getTempArray(console);
    double average = average(temps);
    
    System.out.println();
    System.out.println("Average temperature = " + average(temps));
    System.out.println(daysAboveAverage(temps, average) + " days above average.");
    
    int[] temps2 = {70, 79, 72, 75, 76, 81};
    average = average(temps2);
    
    System.out.println("Average temperature = " +average(temps2));
    System.out.println(daysAboveAverage(temps2, average) + " days above average.");
  }
  
  public static int[] getTempArray(Scanner console) {
    System.out.println("How many days' temperatures? ");
    int numDays = console.nextInt();
    int[] temps = new int[numDays];
    
    for (int i = 0; i < temps.length; i++) {
      System.out.print("Day " + (i + 1) + "'s high temperature: ");
      temps[i] = console.nextInt();
    }
    
    return temps;
  }
  
  public static double average(int[] temps) {
    double sum = 0;
    
    for (int i = 0; i < temps.length; i++)
      sum += temps[i];
      
      return sum / temps.length;
  }
    
  public static int daysAboveAverage(int[] temps, double average) {
    int daysAbove = 0;
      
    for (int i = 0; i < temps.length; i++)
      if (temps[i] > average)
	daysAbove++;
      
    return daysAbove;
  }
}
{% endhighlight %}

<strong>Class Exercise 22:</strong> Array process 2 / Command line test

{% highlight java %}
import java.util.*;

public class ArrayProcess2 {
  public static void main(String[] args) {
    String[] weekDays = {"Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday", "Sunday"};
    
    System.out.println(weekDays);
    System.out.println(Arrays.toString(weekDays));
      
    String[] weekEnds = Arrays.copyOfRange(weekDays, 5, 7);
      
    System.out.println(Arrays.toString(weekEnds));
    System.out.println();
      
    int[] numbers1 = {5, 4, 3, 2, 1};
      
    System.out.println(numbers1);
    printArray(numbers1);
    System.out.println(Arrays.toString(numbers1));
      
    int[] numbers2 = Arrays.copyOf(numbers1, 10);
      
    System.out.println(Arrays.toString(numbers2));
    Arrays.sort(numbers1);
      
    int[] numbers3 = {1, 2, 3, 4, 5};
      
    if (numbers1 == numbers3)
      System.out.println(numbers1 + " equals " + numbers3);
    else 
      System.out.println(numbers1 + " does not equal " + numbers3);

    if (Arrays.equals(numbers1, numbers3))
      System.out.println(Arrays.toString(numbers1) + " equals " + Arrays.toString(numbers3));
    else
      System.out.println(Arrays.toString(numbers1) + " does not equal " + Arrays.toString(numbers3));
  }
    
  public static void printArray(int[] a) {
    for (int num:a)
      System.out.print(num + " ");
	
    System.out.println();
  }
}
{% endhighlight %}

{% highlight java %}
import java.util.*;
import java.io.*;

public class CommandLineTest {
  public static void main(String[] args) {
    try {
      Scanner input = new Scanner(new File(args[0]));
      int count = 0;
      
      while (input.hasNext() && count < Integer.parseInt(args[1])) {
        int num = Integer.parseInt(input.next());
	
	System.out.print(num + " ");
	count++;
      }
      
      System.out.println();
    } catch (FileNotFoundException e) {
      System.out.println("The file does not exist.");
    }
  }
}
{% endhighlight %}


<strong>Class Exercise 23:</strong> 2D array

{% highlight java %}
public class TwoDArray {
  public static void main(String[] args) {
    int[][] sudoku = {% raw %}{{1, 2, 3}, {2, 3, 1}, {3, 2, 1}}{% endraw %};
		
    for (int i = 0; i < sudoku.length; i++) {
      for (int j = 0; j < sudoku[i].length; j++) {
        System.out.print(sudoku[i][j] + " ");
      }

      System.out.println();
    }

    System.out.println();
  }
}
{% endhighlight %}


<strong>Class Exercise 24:</strong> Array list practice

{% highlight java %}
import java.util.*;

public class ArrayListPractice {
  public static void main(String[] args) {
    ArrayList<Integer> list1 = new ArrayList<Integer>();
	
    list1.add(10);
    list1.add(20);
    list1.add(0, 30);
    
    System.out.println(list1);
    
    list1.remove(1);
    
    System.out.println(list1);
    System.out.println(list1.size());
    
    update(list1);
    
    System.out.println(list1);
    
    list1.clear();
    
    System.out.println(list1);
  }
  
  public static void update(ArrayList<Integer> list) {
    for (int i = 0; i < list.size(); i++)
      list.set(i, list.get(i) + 1);
  }
}
{% endhighlight %}
				    
				    
<strong>Class Exercise 25:</strong> Array list practice

{% highlight java %}
import java.util.*;

public class ArrayListTest {
  public static void main(String[] args) {
    ArrayList<String> words = new ArrayList<String>();
	
    for (int i = 0; i < args.length; i++)
      words.add(args[i]);
    
    System.out.println(words);
    
    String word = "be";
    
    if (words.contains(word))
      System.out.println("Yes, the list contains the word: " + word);
    else 
      System.out.println("No, the list does not contain the word: " + word);
    
    System.out.println();
    
    duplicateWord(words);
    
    System.out.println(words);
  }
  
  public static void duplicateWord(ArrayList<String> list) {
    for (int i = 0; i < list.size(); i += 2)
      list.add(i + 1, list.get(i));
  }
}
{% endhighlight %}
