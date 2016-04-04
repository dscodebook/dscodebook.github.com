---
layout: post
title:  "Factorial.cs.cs"
date:   2016-04-03 19:59:20 +0530
categories: Sorting
---

{% highlight csharp %}


void Main()
{
	Factorial(-1).Dump();
}

int Factorial(int n)
{
	if (n < 0 || n == 1)
		return 1;
	return n * Factorial(n - 1);
}


{% endhighlight %}