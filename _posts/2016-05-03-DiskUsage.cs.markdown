---
layout: post
title:  "DiskUsage.cs"
date:   2016-04-03 19:59:20 +0530
categories: Sorting
---

{% highlight csharp %}


void Main()
{
		DirSearch(@"C:\temp").Dump();
}

static int DirSearch(string sDir)
{
	int size=0;
	try
	{
		foreach (string d in Directory.GetDirectories(sDir))
		{
			foreach (string f in Directory.GetFiles(d))
			{
				Console.WriteLine(f);
			}
			DirSearch(d);
		}
	}
	catch (System.Exception excpt)
	{
		Console.WriteLine(excpt.Message);
	}
	return size;
	
}


{% endhighlight %}