---
layout: post
title: "2019 Kakao Blind Recruitment"
categories:
  - 2019 Kakao Blind Recruitment
tags:
  - C++
  - 2019 Kakao Blind Recruitment
  - Programmers
last_modified_at: 2020-09-05-23-00
---

<strong> 문제 1:</strong> 실패율

<strong>문제 설명</strong>

![crane_game_101.png](/assets/images/2020-09-03-23-33-2019-카카오-개발자-겨울-인턴십/crane_game_101.png)

{% highlight txt %}
슈퍼 게임 개발자 오렐리는 큰 고민에 빠졌다. 그녀가 만든 프랜즈 오천성이 대성공을
거뒀지만, 요즘 신규 사용자의 수가 급감한 것이다. 원인은 신규 사용자와 기존 사용자
사이에 스테이지 차이가 너무 큰 것이 문제였다.
이 문제를 어떻게 할까 고민 한 그녀는 동적으로 게임 시간을 늘려서 난이도를
조절하기로 했다. 역시 슈퍼 개발자라 대부분의 로직은 쉽게 구현했지만, 실패율을
구하는 부분에서 위기에 빠지고 말았다. 오렐리를 위해 실패율을 구하는 코드를
완성하라.
{% endhighlight %}

{% highlight txt %}
  - 실패율은 다음과 같이 정의한다.
    - 스테이지에 도달했으나 아직 클리어하지 못한 플레이어의 수 / 스테이지에 도달한 플레이어 수
{% endhighlight %}

<strong>제한사항</strong>
{% highlight txt %}
  - 스테이지의 개수 N은 1 이상 500 이하의 자연수이다.
  - stages의 길이는 1 이상 200,000 이하이다.
  - stages에는 1 이상 N + 1 이하의 자연수가 담겨있다.
    - 각 자연수는 사용자가 현재 도전 중인 스테이지의 번호를 나타낸다.
    - 단, N + 1 은 마지막 스테이지(N 번째 스테이지) 까지 클리어 한 사용자를 나타낸다.
  - 만약 실패율이 같은 스테이지가 있다면 작은 번호의 스테이지가 먼저 오도록 하면 된다.
  - 스테이지에 도달한 유저가 없는 경우 해당 스테이지의 실패율은 0 으로 정의한다.
{% endhighlight %}

<strong>입출력 예</strong>

| N | stages | result |
| --- | --- | --- |
| 5 | [2, 1, 2, 6, 2, 4, 3, 3] | [3,4,2,1,5] |
| 4 | [4,4,4,4,4] | [4,1,2,3] |


<strong>입출력 예에 대한 설명</strong>
{% highlight txt %}
입출력 예 #1
1번 스테이지에는 총 8명의 사용자가 도전했으며, 이 중 1명의 사용자가 아직 클리어하지 못했다.
따라서 1번 스테이지의 실패율은 다음과 같다.
  - 1 번 스테이지 실패율 : 1/8
2번 스테이지에는 총 7명의 사용자가 도전했으며, 이 중 3명의 사용자가 아직 클리어하지 못했다.
따라서 2번 스테이지의 실패율은 다음과 같다.
  - 2 번 스테이지 실패율 : 3/7
마찬가지로 나머지 스테이지의 실패율은 다음과 같다.
  - 3 번 스테이지 실패율 : 2/4
  - 4번 스테이지 실패율 : 1/2
  - 5번 스테이지 실패율 : 0/1
각 스테이지의 번호를 실패율의 내림차순으로 정렬하면 다음과 같다.
  - [3,4,2,1,5]
{% endhighlight %}

{% highlight txt %}
입출력 예 #2
모든 사용자가 마지막 스테이지에 있으므로 4번 스테이지의 실패율은 1이며 나머지 스테이지의 실패율은 0이다.
  - [4,1,2,3]
{% endhighlight %}

{% highlight cpp %}
#include <string>
#include <vector>

using namespace std;

vector<int> solution(int N, vector<int> stages) {
    vector<double> rate(N, 0.0);
    vector<int> answer;
    double cnt = 0.0, den = stages.size();
    double max = -99.99;
    decltype(rate.size()) index = 0;
    
    for (auto i = 0; i != N; i++) {
        for (decltype(stages.size()) j = 0; j != stages.size(); j++) {
            if (stages[j] == i + 1) {
                cnt++;
            }
        } 
        cnt ? rate[i] = cnt / den : 0.0;
        den -= cnt;
        cnt = 0.0;
    }
    
    for (decltype(rate.size()) i = 0; i != rate.size(); i++) {
        for (decltype(rate.size()) j = 0; j != rate.size(); j++) {
            if (max < rate[j]) {
                max = rate[j];
                index = j;
            }
        } answer.push_back(index + 1);
        rate[index] = -99.99;
        max = -99.99;
    } return answer;
}
{% endhighlight %}
