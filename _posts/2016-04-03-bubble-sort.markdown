---
layout: post
title:  "Bubble Sort"
date:   2016-04-03 19:59:20 +0530
categories: Sorting
---
Bubble sort, sometimes referred to as sinking sort, is a simple sorting algorithm that repeatedly steps through the list to be sorted, compares each pair of adjacent items and swaps them if they are in the wrong order. The pass through the list is repeated until no swaps are needed, which indicates that the list is sorted. The algorithm, which is a comparison sort, is named for the way smaller elements "bubble" to the top of the list. Although the algorithm is simple, it is too slow and impractical for most problems even when compared to insertion sort.[1] It can be practical if the input is usually in sort order but may occasionally have some out-of-order elements nearly in position.

{% highlight csharp %}
using System;

class myclass
{
    static void Main()
    {
        int[] a = { 4, 6, 9, 83, 34, 45 };
        int temp;

        for (int pass = 1; pass <= a.Length - 2; pass++)
        {
            for (int i = 0; i <= a.Length - 2; i++)
            {
                if (a[i] > a[i + 1])
                {
                    temp = a[i + 1];
                    a[i + 1] = a[i];
                    a[i] = temp;
                }

            }

        }

        Console.WriteLine("The Sorted array");
        foreach (int aa in a)
            Console.Write(aa + " ");

        Console.Read();
    }
}

{% endhighlight %}