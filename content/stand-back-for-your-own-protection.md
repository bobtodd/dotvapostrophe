Title: Stand Back!
subtitle: For your own protection
Date: 2016-05-14 7:47
disqus_identifier: stand-back-for-your-own-protection
slug: stand-back-for-your-own-protection

[TOC]

# In the Beginning

Hey!  Watch out!  Can't you see I'm trying to start a blog here!?!?

This is obviously my first post, where I say nothing in particular, but try to sound intelligent and look web-savvy while I'm at it.  Really what I'm trying to do is make sure I've got all the moving pieces working together.  So expect gratuitous use of

* Sections (to see if the table of contents is working);
* Formulas (to make sure \(\LaTeX\) is compiling);
* Code (to make sure... well... code renders like code).

I'll spare you the details.

# Technobabble

Here's where I'll start to use some technical features of my blog setup.  We'll start with the math.

## Euler's Identity

For the math-lovers among us, perhaps an appropriate formula to quote out of the blue is [Euler's identity](https://en.wikipedia.org/wiki/Euler's_identity).  Typically we see it written $$e^{i\pi} = -1.$$  But as the late [Dr. Guy](http://www.utexas.edu/faculty/council/2011-2012/memorials/guy.html), a pedagogical master, was keen to point out, writing it as $$e^{i\pi} - 1 = 0$$ ensures that we relate all of the most important numbers in mathematics to one another.  Gotta love Dr. Guy.

## Euler Method

Since we're showing off Euler's brilliance, we might use the [Euler method](https://en.wikipedia.org/wiki/Euler_method) as our example of code rendering.  Of course Euler's method refers to the solving of an ordinary differential equation (ODE)

$$y'(t) = f(t, y(t)), \qquad \text{with $y(t_0) = y_0$}$$

by means of determining a step-size $h$, then obtaining a subsequent value of $y$ by adding to the previous value of $y$ the value of $f$ at that $y$, multiplied by the step-size:

$$y_{k+1} = y_k + h f(t_k, y_k),$$

where $h := (t_n - t_0)/n,$ and $t_{i+1} = t_i + h$, for some integer $n$ determining the number of iterations.  In code, this becomes

```python
def Euler(f, tzero, tmax, yzero, n):
	h = (tmax - tzero)/float(n)
	t = [tzero]
	y = [yzero]
	
	for i in range(n):
		y.append( y[-1] + h * f(t[-1], y[-1]) )
		t.append( t[-1] + h )
	
	return t, y
```

Hopefully that about captures the spirit.

# Closing

I'm sure you've had about enough of this post, so we'll leave it at that.