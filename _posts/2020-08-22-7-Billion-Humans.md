---
layout: post
title: "7-Billion_Humans_Solution"
categories:
  - 7 Billion Humans
tags:
  - 7 Billion Humans
  - Game
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


<storng>Year 11:</strong> Injection Sites 1 (size)

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


<storng>Year 11:</strong> Injection Sites 1 (speed)

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


<strong>Year 22:</storng> Number Royale (both)

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
