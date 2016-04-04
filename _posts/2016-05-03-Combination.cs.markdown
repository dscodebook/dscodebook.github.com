---
layout: post
title:  "Combination.cs"
date:   2016-04-03 19:59:20 +0530
categories: Sorting
---

{% highlight csharp %}


void Main()
{
	int [] arr = { 1, 2, 3, 4, 5 };
	int r = 3;
	int n = arr.Length;
	PrintCombination(arr, n, r);
}

/* arr[]  ---> Input Array
   data[] ---> Temporary array to store current combination
   start & end ---> Staring and Ending indexes in arr[]
   index  ---> Current index in data[]
   r ---> Size of a combination to be printed */
static void CombinationUtil(int[] arr, int n, int r, int index,int[] data, int i)
{
	// Current combination is ready to be printed, print it
	if (index == r)
	{
		for (int j = 0; j < r; j++)
			Console.Write(data[j] + " ");
		Console.WriteLine();
		return;
	}

	// When no more elements are there to put in data[]
	if (i >= n)
		return;

	// current is included, put next at next location
	data[index] = arr[i];
	CombinationUtil(arr, n, r, index + 1, data, i + 1);

	// current is excluded, replace it with next (Note that
	// i+1 is passed, but index is not changed)
	CombinationUtil(arr, n, r, index, data, i + 1);
}

// The main function that prints all combinations of size r
// in arr[] of size n. This function mainly uses combinationUtil()
static void PrintCombination(int[] arr, int n, int r)
{
	// A temporary array to store all combination one by one
	int[] data = new int[r];

	// Print all combination using temprary array 'data[]'
	CombinationUtil(arr, n, r, 0, data, 0);
}

{% endhighlight %}