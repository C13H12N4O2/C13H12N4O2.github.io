---
layout: post
title: "7 BillionHumans Solutions"
categories:
  - 7 Billion Humans
tags:
  - 7 Billion Humans
  - Game
last_modified_at: 2020-08-22-23-58-45
---

<strong>Year 02:</strong> Welcome, New Employees (both)

{% highlight txt %}
step s
pickUp
drop
{% endhighlight %}


<strong>Year 03:</strong> Transport Squad (both)

{% highlight txt %}
step s
pickUp
step s
step s
drop
{% endhighlight %}


<strong>Year 04:</strong> Long Distance Delivery (both)

{% highlight txt %}
step e
pickUp
a:
step e
jump a
{% endhighlight %}


<strong>Year 05:</strong> An Important Decision (both)

{% highlight txt %}
if w == datacube:
    a:
    step w
    jump a
endif
b:
step e
jump b
{% endhighlight %}


<strong>Year 06:</strong> Little Exterminator 1 (both)
{% highlight txt %}
step s
step sw
step sw
step se
step e
step se
step s
step s
pickUp
{% endhighlight %}


<strong>Year 07:</strong> Collation Station (size)

{% highlight txt %}
a:
step s
pickUp c
if s == hole:
    drop
endif
jump a
{% endhighlight %}


<strong>Year 07:</strong> Collation Station (speed)

{% highlight txt %}
a:
if c == datacube:
    pickUp c
    b:
    step s
    if s == hole:
        drop
    else:
        jump b
  endif
else:
    step s
    jump a
endif
{% endhighlight %}


<strong>Year 09:</strong> Dynamic Angles (both)

{% highlight txt %}
pickUp s
a:
if nw == datacube:
    drop
endif
jump a
{% endhighlight %}


<strong>Year 10:</strong> Emergency Escapades (size)

{% highlight txt %}
a:
if c == 1:
    step n
endif
if c == 2:
    step e
endif
if c == 3:
    step s
endif
if c == 4 or
   c != datacube
    step w
endif
jump a
{% endhighlight %}


<strong>Year 10:</strong> Emergency Escapades (speed)

{% highlight txt %}
step w
step w
a:
step w
if c != datacube:
    jump a
endif
if c == datacube and
   w != hole:
    step w
    b:
    c:
    d:
    e:
    step sw
    step s
    step sw
    step w
    step w
    step w
    step nw
    step n
    step n
    step n
    step n
    step nw
else:
    if nw != hole and
       s  != wall:
        step nw
        jump b
    endif
    if sw != hole and
       s  != wall:
        step sw
        jump c
    endif
    if s == wall:
        step n
        step nw
        jump d
    endif
    if ne == hole and
       s  != wall:
        step sw
        jump e
    endif
endif
{% endhighlight %}


<strong>Year 11:</strong> Injection Sites 1 (size)

{% highlight txt %}
pickUp s
step s
step s
a:
step s
step s
if c == nothing:
    drop
endif
jump a
{% endhighlight %}


<strong>Year 11:</strong> Injection Sites 1 (speed)

{% highlight txt %}
pickUp s
a:
step s
if w == datacube and
   c == nothing:
    drop
endif
jump a
{% endhighlight %}


<strong>Year 12:</strong> Unzip (both)

{% highlight txt %}
pickUp c
a:
if w == wall or
   sw == worker:
    dtep n
    drop
endif
if nw == worker:
    step s
    drop
endif
jump a
{% endhighlight %}


<strong>Year 13:</strong> Injection Sites 2 (speed)

{% highlight txt %}
step s
pickUp c
step se
step se
drop
step sw
step sw
drop
step se
step se
step e
step e
step e
drop
step sw
step s
drop
{% endhighlight %}


<strong>Year 14:</strong> Intro to Shredding (size)

{% highlight txt %}
step s
pickUp c
step s
giveTo s
{% endhighlight %}


<strong>Year 14:</strong> Intro to Shredding (speed)

{% highlight txt %}
if s == datacube:
    step s
    pickUp c
    step s
    giveTo s
endif
{% endhighlight %}


<strong>Year 15:</strong> Shred Lines (size)

{% highlight txt %}
a:
if c == datacube:
    pickUp c
    b:
    if s == shredder:
        giveTo s
    else:
        step s
        jump b
    endif
endif
step n
jump a
{% endhighlight %}


<strong>Year 15:</strong> Shred Lines (speed)

{% highlight txt %}
a:
step n
if n == datacube:
    pickUp n
    b:
    if s == shredder:
        giveTo s
        step n
    else:
        step s
        step s
        jump b
    endif
endif
jump a
{% endhighlight %}


<strong>Year 16:</strong> Little Exterminator 2 (size)

{% highlight txt %}
a:
if c == a datacube:
    pickUp c
    b:
    step e
    if s == shredder:
        giveTo s
    endif
    jump b
endif
step s
jump a
{% endhighlight %}


<strong>Year 16:</strong> Little Exterminator 2 (speed)

{% highlight txt %}
step s
a:
step s
if c != datacube:
    jump a
endif
pickUp c
step e
step e
step e
b:
step e
if s == a shredder:
    giveTo s
endif
jump b
{% endhighlight %}


<strong>Year 17:</strong> Content Creators (both)

{% highlight txt %}
pickUp s
{% endhighlight %}


<strong>Year 18:</strong> Uniquely Disposed (both)

{% highlight txt %}
pickUp w
step sw
a:
if s == a shredder:
    giveTo s
    end
endif
step se
jump a
{% endhighlight %}


<strong>Year 19:</strong> Content Creators Bug Fix (both)

{% highlight txt %}
a:
takeFrom s
giveTo se
step w
jump a
{% endhighlight %}


<strong>Year 20:</strong> Reverse Line (both)

{% highlight txt %}
pickUp s
a:
if se == hole:
    step s
    b:
    if w == hole or
       w == datacube:
        drop
    endif
    step w
    jump b
endif
step e
jump a
{% endhighlight %}



<strong>Year 21:</strong> Big Data (size)

{% highlight txt %}
step s
a:
takeFrom s
if my item < 50:
    giveTo sw
    step e
endif
jump a
{% endhighlight %}


<strong>Year 21:</strong> Big Data (speed)

{% highlight txt %}
a:
step s
if s == printer:
    takeFrom s
    b:
    if my item >= 50:
        step nw
        c:
        if n == wall or
    	     n == worker:
    	      end
    	  endif
        step n
        jump c
    endif
    giveTo sw
    takeFrom se
    jump b
else:
    d:
    if s != worker:
        jump a
    endif
    jump d
endif
{% endhighlight %}


<strong>Year 22:</strong> Number Royale (both)

{% highlight txt %}
pickUp s
a:
if my item < e or
   my item < w:
    b:
    step s
    jump b
endif
step e
jump a
{% endhighlight %}


<strong>Year 23:</strong> Sorting Hall (both)

{% highlight txt %}
pickUp s
a:
if my item > e:
    step e
endif
if my item < w:
    step w
endif
jump a
{% endhighlight %}


<strong>Year 24:</strong> Budget Brigade 1 (size)

{% highlight txt %}
a:
if s == hole or
   s == printer:
    takeFrom s
    giveTo e
    jump a
endif
b:
if s == shredder and
   my item == datacube:
    giveTo s
endif
jump b
{% endhighlight %}


<strong>Year 24:</strong> Budget Brigade 1 (speed)

{% highlight txt %}
if s == printer:
    a:
    takeFrom s
    giveTo e
    jump a
endif
if s == shredder:
    b:
    if my item == datacube:
        giveTo s
    endif
    jump b
endif
c:
if my item == datacube:
    giveTo e
endif
jump c
{% endhighlight %}


<strong>Year 25:</strong> My First Shredding Memory (size)

{% highlight txt %}
mem 1 = nearest shredder
a:
mem 2 = nearest datacube
pickUp mem 2
giveTo mem 1
jump a
{% endhighlight %}


<strong>Year 25:</strong> My First Shredding Memory (speed)

{% highlight txt %}
mem 1 = nearest shredder
a:
mem 2 = nearest datacube
pickUp mem 1
if my item == nothing:
    end
endif
giveTo mem 2
jump a
{% endhighlight %}


<strong>Year 26:</strong> Budget Brigade 2 (size)

{% highlight txt %}
a:
if my item == datacube and
   s == shredder:
    giveTo s
endif
if w == hole and
   e == hole:
    takeFrom s
endif
giveTo n
if my item >= 50:
    giveTo e
else:
    giveTo w
endif
jump a
{% endhighlight %}


<strong>Year 26:</strong> Budget Brigade 2 (speed)

{% highlight txt %}
if s == printer:
    a:
    takeFrom s
    giveTo n
    jump a
endif
if w == hole and
   e == hole:
    b:
    if my item == datacube:
        giveTo n
    endif
    jump b
endif
if w == worker and
   e == worker and
   s == worker:
    c:
    d:
    if my item == datacube:
        if my item >= 50:
            giveTo e
        endif
        if my item < 50:
	    giveTo w
        endif
    endif
    jump c
endif
if n == hole and
   s == hole:
    jump d
endif
if s == shredder:
    e:
    if my item == datacube:
        giveTo s
    endif
    jump e
endif
{% endhighlight %}


<strong>Year 28:</strong> Neural Pathways (both)

{% highlight txt %}
mem 1 = nearest datacube
mem 2 = nearest shredder
pickUp mem 1
giveTo mem 2
{% endhighlight %}


<strong>Year 29:</strong> Biometric Access (both)

{% highlight txt %}
mem 1 = nearest shredder
a:
mem 2 = nearest datacube
pickUp mem 2
giveTo mem 1
jump a
{% endhighlight %}


<strong>Year 30:</strong> Fill the Floor (size)

{% highlight txt %}
mem 1 = nearest printer
a:
takeFrom mem 1
step a
drop
jump a
{% endhighlight %}


<strong>Year 30:</strong> Fill the Floor (speed)

{% highlight txt %}
mem 1 = nearet printer
mem 2 = nearet wall
a:
takeFrom mem 1
step mem 2
b:
if c != datacube:
    drop
    mem 2 = nearest datacube
else:
    step a
    jump b
endif
jump a
{% endhighlight %}


Year 31 - Checkerboard Organization (speed).txt

{% highlight txt %}
mem 1 = nearest printer
mem 2 = nearest datacube
a:
takeFrom mem 1
step mnem 2
b:
if c == datacube:
    step nw, ne, sw, se
    jump b
else:
    drop
    mem 2 = nearest datacube
endif
jump a
{% endhighlight %}


<strong>Year 32:</strong> - Creative Writhing (size)

{% highlight txt %}
a:
step a
pickUp c
write 99
drop
jump a
{% endhighlight %}


<strong>Year 32:</strong> - Creative Writhing (speed)

{% highlight txt %}
step s
a:
b:
c:
pickUp c
write 99
drop
if s == 0:
    step s
    jump a
endif
if e == 0:
    step e
    jump b
endif
step w
jump c
{% endhighlight %}


<strong>Year 33:</strong> Data Backup Day (size)

{% highlight txt %}
mem 1 = set w
mem 2 = set e
if mem 1 < mem 2:
    pickUp mem 2
    write mem 1
endif
pickUp mem 1
write mem 2
drop
{% endhighlight %}


<strong>Year 33:</strong> Data Backup Day (speed)

{% highlight txt %}
mem 1 = set w
mem 2 = set e
if mem 1 < mem 2:
    pickUp mem 2
    write mem 1
else:
    pickUp mem 1
    write mem 2
endif
drop
{% endhighlight %}


<strong>Year 34:</strong> Seek and Destroy 1 (size)

{% highlight txt %}
mem 1 = set 99
a:
if n != a wall:
    step n
    if mem 1 > c and
       c == datacube:
        mem 1 = set c
    endif
    jump a
endif 
pickUp mem 1
mem 2 = nearest shredder
giveTo mem 2
{% endhighlight %}


<strong>Year 35:</strong> Intro to Calc for Art Majors (both)

{% highlight txt %}
pickUp s
mem 1 = calc my item + 1
write mem 1
drop
{% endhighlight %}


<strong>Year 36:</strong> Seek and Destroy 2 (size)

{% highlight txt %}
mem 2 = nearest shredder
a:
mem 1 = set 99
b:
step n
if n != wall:
    if c == datacube and
       mem 1 >= c:
        mem 1 = set c
    endif
    jump b
endif
pickUp mem 1
giveTo mem 2
jump a
{% endhighlight %}


<strong>Year 36:</strong> Seek and Destroy 2 (speed)

{% highlight txt %}
mem 1 = nearest shredder
a:
mem 2 = set 99
b:
if c != datacube:
    step n
    jump b
endif
c:
if n != wall:
    if mem 2 >= c:
        mem 2 = set c
    endif
    step n
    jump c
endif
pickUp mem 2
if mem 2 == nothing:
    end
endif
giveTo mem 1
jump a
{% endhighlight %}


<strong>Year 37:</strong> Dangerous Spreadsheeting (speed)

{% highlight txt %}
jump d
a:
if c == datacube:
    b:
    mem 1 = calc mem 1 + c
endif
if e == hole:
    step ne
    c:
    if se == hole:
        step e
        jump c
    endif
    step se
    jump b
endif
d:
step e
if e == wall:
    pickUp c
    write mem 1
    drop
    end
endif
jump a
{% endhighlight %}


<strong>Year 38:</strong> Seek and Destroy 3 (-)

{% highlight txt %}
mem 1 = nearest shredder
mem 2 = set 99
mem 3 = nearest wall
if w == wall:
    b:
    if n != a wall:
        step n
        jump b
    endif
    c:
    if e == worker:
        takeFrom e
        giveTo mem 1
    endif
    jump c
endif
pickUp mem 2
step mem 3
mem 4 = nearest hole
if e == hole and
   s == wall:
    step nw
    d:
    if mem 2 >= s:
        mem 2 = set s
    endif
    step w
    if w == wall:
        if my item > mem 2:
            drop
            takeFrom mem 2
        endif
        giveTo mem 1
    endif
    jump d
endif
{% endhighlight %}


<strong>Year 39:</strong> Printing Etiquette 1 (size)

{% highlight txt %}
mem 1 = nearest printer
a:
if mem 2 != 5:
    takeFrom mem 1
    b:
    if c != nothing:
        step a
        jump b
    endif
    drop
    mem 2 = calc mem 2 + 1;
    jump a
endif
{% endhighlight %}


<strong>Year 39:</strong> Printing Etiquette 1 (speed)

{% highlight txt %}
mem 1 = nearet printer
takeFrom mem 1
a:
if c != nothing:
    step a
    jump a
endif
drop
mem 2 = nearest datacube
takeFrom mem 1
step mem 2
b:
if c != nothing:
    step a
    jump b
endif
mem 2 = nearest datacube
takeFrom mem 1
step mem 2
c:
if c != nothing:
    step a
    jump c
endif
drop
mem 2 = nearest datacube
takeFrom mem 1
step mem 2
d:
if c != nothing:
    step a
    jump d
endif
drop
mem 2 = nearest datacube
takeFrom mem 1
step mem 2
e:
if c != nothing:
    step a
    jump e
endif
drop
{% endhighlight %}


<strong>Year 40:</strong> Printing Etiquette 2 (size)

{% highlight txt %}
mem 1 = nearest printer
a:
takeFrom mem 1
mem 2 = calc mem 2 + 1
write mem 2
b:
if c != nothing:
    step a
    jump b
endif
drop
if mem 2 != 5:
    jump a
endif
{% endhighlight %}
