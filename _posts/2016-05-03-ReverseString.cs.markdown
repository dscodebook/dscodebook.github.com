---
layout: post
title:  "ReverseString.cs"
date:   2016-04-03 19:59:20 +0530
categories: Sorting
---

{% highlight csharp %}
<Query Kind="Program" />

void Main()
{
	Reverse("santosh").Dump();
}

public string Reverse(string str)
{
		if(str.Length==1)
			return str;
		string result= str[str.Length-1]+Reverse(str.Substring(0,str.Length-1));
		return result;
}


{% endhighlight %}