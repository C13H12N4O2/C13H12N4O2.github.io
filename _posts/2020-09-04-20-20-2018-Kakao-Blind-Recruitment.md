---
layout: post
title: "2018 Kakao Blind Recruitment"
categories:
  - 2018 Kakao Blind Recruitment
tags:
  - C++
  - 2018 Kakao Blind Recruitment
  - Programmers
last_modified_at: 2020-09-04-20-20
---

<strong> 문제 1:</strong> 비밀지도

<strong>문제 설명</strong>
{% highlight txt %}
네오는 평소 프로도가 비상금을 숨겨놓는 장소를 알려줄 비밀지도를 손에 넣었다.
그런데 이 비밀지도는 숫자로 암호화되어 있어 위치를 확인하기 위해서는 암호를
해독해야 한다. 다행히 지도 암호를 해독할 방법을 적어놓은 메모도 함께 발견했다.
{% endhighlight %}

{% highlight txt %}
1. 지도는 한 변의 길이가 n인 정사각형 배열 형태로, 각 칸은 "공백"(" ")
   또는"벽"("#") 두 종류로 이루어져 있다.
2. 전체 지도는 두 장의 지도를 겹쳐서 얻을 수 있다. 각각 "지도 1"과
   "지도 2"라고 하자. 지도 1 또는 지도 2 중 어느 하나라도 벽인 부분은 전체
   지도에서도 벽이다. 지도 1과 지도 2에서 모두 공백인 부분은 전체 지도에서도
   공백이다.
3. "지도 1"과 "지도 2"는 각각 정수 배열로 암호화되어 있다.
4. 암호화된 배열은 지도의 각 가로줄에서 벽 부분을 1, 공백 부분을 0으로
   부호화했을 때 얻어지는 이진수에 해당하는 값의 배열이다.
{% endhighlight %}

![crane_game_101.png](/assets/images/2020-09-03-23-33-2019-카카오-개발자-겨울-인턴십/crane_game_101.png)

{% highlight txt %}
네오가 프로도의 비상금을 손에 넣을 수 있도록, 비밀지도의 암호를 해독하는 작업을
도와줄 프로그램을 작성하라.
{% endhighlight %}

<strong>입력 형식</strong>
{% highlight txt %}
입력으로 지도의 한 변 크기 n 과 2개의 정수 배열 arr1, arr2가 들어온다.
{% endhighlight %}

{% highlight txt %}
1 ≦ n ≦ 16
arr1, arr2는 길이 n인 정수 배열로 주어진다.
정수 배열의 각 원소 x를 이진수로 변환했을 때의 길이는 n 이하이다.
즉, 0 ≦ x ≦ $2^n$ - 1을 만족한다.
{% endhighlight %}

<strong>출력 형식</strong>

{% highlight txt %}
1 ≦ n ≦ 16
원래의 비밀지도를 해독하여 '#', 공백으로 구성된 문자열 배열로 출력하라.
{% endhighlight %}

<strong>입출력 예제</strong>

| 매개변수 | 값 |
| --- | --- |
| n | 5 |
| arr1 | [9, 20, 28, 18, 11] |
| arr2 | [30, 1, 21, 17, 28] |
| 출력 | ["#####","# # #", "### #", "# ##", "#####"] |

| 매개변수 | 값 |
| --- | --- |
| n | 6 |
| arr1 | [46, 33, 33 ,22, 31, 50] |
| arr2 | [27 ,56, 19, 14, 14, 10] |
| 출력 | ["######", "### #", "## ##", " #### ", " #####", "### # "] |

{% highlight cpp %}
#include <string>
#include <vector>

using namespace std;

vector<string> solution(int n, vector<int> arr1, vector<int> arr2) {
    vector<string> answer;
    vector<int> vi1;
    vector<vector<int>> vi3, vi4;
    string line;
    int temp;

    for (decltype(arr1.size()) i = 0; i != arr1.size(); i++) {
        for (decltype(arr1.size()) j = 0; j != arr1.size(); j++) {
            if (arr1[i] % 2) {
                vi1.push_back(1);
            } else {
                vi1.push_back(0);
            } arr1[i] /= 2;
        }
        for (decltype(vi1.size()) j = 0; j != vi1.size() / 2; j++) {
            temp = vi1[j];
            vi1[j] = vi1[vi1.size() - j - 1];
            vi1[vi1.size() - j - 1] = temp;
        } vi3.push_back(vi1);
        vi1.clear();
    }  
    
    for (decltype(arr2.size()) i = 0; i != arr2.size(); i++) {
        for (decltype(arr2.size()) j = 0; j != arr2.size(); j++) {
            if (arr2[i] % 2) {
                vi1.push_back(1);
            } else {
                vi1.push_back(0);
            } arr2[i] /= 2;
        }
        for (decltype(vi1.size()) j = 0; j != vi1.size() / 2; j++) {
            temp = vi1[j];
            vi1[j] = vi1[vi1.size() - j - 1];
            vi1[vi1.size() - j - 1] = temp;
        } vi4.push_back(vi1);
        vi1.clear();
    }
    
    for (decltype(vi3.size()) i = 0; i != vi3.size(); i++) {
        for (decltype(vi3.size()) j = 0; j != vi3.size(); j++) {
            vi3[i][j] |= vi4[i][j];
        }
    }
    
    for (auto v : vi3) {
        for (auto i : v) {
            if (i)
                line += '#';
            else
                line += ' ';
        } answer.push_back(line);
        line.clear();
    } return answer;
}
{% endhighlight %}
