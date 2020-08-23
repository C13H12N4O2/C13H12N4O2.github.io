---
layout: post
title: "Insertion Sort"
categories:
  - Algorithm
tags:
  - Algorithm
  - Sort
  - C++
last_modified_at: 2020-08-23-22-34-30
---

{% highlight cpp %}
void Swap(int* ary, int left, int right) {
  int temp = ary[left];
  ary[left] = ary[right];
  ary[right] = temp;
}

int* Sort(int* ary, int size) {
  int i = 0;

  while (i < size - 1) {
    if (ary[i + 1] < ary[i]) {
      Swap(ary, i + 1, i);
      
      for (int j = i; j > 0; j--) {
        if (ary[j] > ary[j - 1]) {
          break;
        } else {
          Swap(ary, j, j - 1);
        }
      }
    }

    i++;
  }

  return ary;
}
{% endhighlight %}
