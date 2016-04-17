---
layout: post
title:  "Permutation.cs"
date:   2016-04-03 19:59:20 +0530
categories: Sorting
---
Write a program to print all permutations of a given string

{% highlight csharp %}


void Main()
{
	Permute(new[] { 'a', 'b', 'c','d' }, 0, 4);
}

static void Swap(ref char a, ref char b)
{
	char temp = a;
	a = b;
	b = temp;

}
static void Permute(char[] str, int i, int n)
{
	if (i == n - 1)
		Console.WriteLine(str);
	else
	{
		for (int j = i; j < n; j++)
		{
			Swap(ref str[i], ref str[j]);
			Permute(str, i + 1, n);
			Swap(ref str[i], ref str[j]);

		}
	}
}


{% endhighlight %}
