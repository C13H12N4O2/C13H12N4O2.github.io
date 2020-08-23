---
layout: post
title: "Selection Sort"
categories:
  - Algorithm
tags:
  - Algorithm
  - Sort
  - C++
last_modified_at: 2020-08-23-22-42-00
---

{% highlight cpp %}
void Swap(int* ary, int left, int right) {
  int temp = ary[left];
  ary[left] = ary[right];
  ary[right] = temp;
}

int* Sort(int* ary, int size) {
  for (int i = 0; i < size; i++) {
    for (int j = i + 1; j < size; j++) {
      if (ary[i] > ary[j]) {
        Swap(ary, i, j);
      }
    }
  }

  return ary;
}
{% endhighlight %}
