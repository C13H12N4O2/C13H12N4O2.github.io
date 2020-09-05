---
layout: post
title: "2018 Kakao Blind Recruitment"
categories:
  - 2018 Kakao Blind Recruitment
tags:
  - C++
  - 2018 Kakao Blind Recruitment
  - Programmers
last_modified_at: 2020-09-05-23-15
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

![secret1.png](/assets/images/2020-09-04-20-20-2018-Kakao-Blind-Recruitment/secret1.png)

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
    vector<vector<int>> board1, board2;
    string line;
    int temp;

    for (decltype(arr1.size()) i = 0; i != arr1.size(); i++) {
        for (decltype(arr1.size()) j = 0; j != arr1.size(); j++) {
            arr1[i] % 2 ? vi1.push_back(1) : vi1.push_back(0);
            arr1[i] /= 2;
        }
        for (decltype(vi1.size()) j = 0; j != vi1.size() / 2; j++) {
            temp = vi1[j];
            vi1[j] = vi1[vi1.size() - j - 1];
            vi1[vi1.size() - j - 1] = temp;
        } board1.push_back(vi1);
        vi1.clear();
    }  
    
    for (decltype(arr2.size()) i = 0; i != arr2.size(); i++) {
        for (decltype(arr2.size()) j = 0; j != arr2.size(); j++) {
            arr2[i] % 2 ? vi1.push_back(1) : vi1.push_back(0);
            arr2[i] /= 2;            
        }
        for (decltype(vi1.size()) j = 0; j != vi1.size() / 2; j++) {
            temp = vi1[j];
            vi1[j] = vi1[vi1.size() - j - 1];
            vi1[vi1.size() - j - 1] = temp;
        } board2.push_back(vi1);
    }
    
    for (decltype(board1.size()) i = 0; i != board1.size(); i++) {
        for (decltype(board1.size()) j = 0; j != board1.size(); j++) {
            board1[i][j] |= board2[i][j];
        }
    }
    
    for (auto v : board1) {
        for (auto i : v) {
            i ? line += '#' : line += ' ';
        } answer.push_back(line);
        line.clear();
    } return answer;
}
{% endhighlight %}


<strong> 문제 2:</strong> 다트 게임

<strong>문제 설명</strong>

{% highlight txt %}
카카오톡에 뜬 네 번째 별! 심심할 땐? 카카오톡 게임별~
{% endhighlight %}

![secret1.png](/assets/images/2020-09-04-20-20-2018-Kakao-Blind-Recruitment/secret1.png)

{% highlight txt %}
카카오톡 게임별의 하반기 신규 서비스로 다트 게임을 출시하기로 했다. 다트 게임은
다트판에 다트를 세 차례 던져 그 점수의 합계로 실력을 겨루는 게임으로, 모두가
간단히 즐길 수 있다.
갓 입사한 무지는 코딩 실력을 인정받아 게임의 핵심 부분인 점수 계산 로직을 맡게
되었다. 다트 게임의 점수 계산 로직은 아래와 같다.
{% endhighlight %}

{% highlight txt %}
1. 다트 게임은 총 3번의 기회로 구성된다.
2. 각 기회마다 얻을 수 있는 점수는 0점에서 10점까지이다.
3. 점수와 함께 Single(S), Double(D), Triple(T) 영역이 존재하고 각
   영역 당첨 시 점수에서 1제곱, 2제곱, 3제곱 (점수1 , 점수2 , 점수3 )으로
   계산된다.
4. 옵션으로 스타상(*) , 아차상(#)이 존재하며 스타상(*) 당첨 시 해당 점수와
   바로 전에 얻은 점수를 각 2배로 만든다. 아차상(#) 당첨 시 해당 점수는
   마이너스된다.
5. 스타상(*)은 첫 번째 기회에서도 나올 수 있다. 이 경우 첫 번째 스타상(*)의
   점수만 2배가 된다. (예제 4번 참고)
6. 스타상(*)의 효과는 다른 스타상(*)의 효과와 중첩될 수 있다. 이 경우 중첩된
   스타상(*) 점수는 4배가 된다. (예제 4번 참고)
7. 스타상(*)의 효과는 아차상(#)의 효과와 중첩될 수 있다. 이 경우 중첩된
   아차상(#)의 점수는 -2배가 된다. (예제 5번 참고)
8. Single(S), Double(D), Triple(T)은 점수마다 하나씩 존재한다.
9. 스타상(*), 아차상(#)은 점수마다 둘 중 하나만 존재할 수 있으며, 존재하지
   않을 수도 있다.
{% endhighlight %}

{% highlight txt %}
0~10의 정수와 문자 S, D, T, *, #로 구성된 문자열이 입력될 시 총점수를
반환하는 함수를 작성하라.
{% endhighlight %}


<strong>입력 형식</strong>
{% highlight txt %}
"점수|보너스|[옵션]"으로 이루어진 문자열 3세트.
예) 1S2D*3T
점수는 0에서 10 사이의 정수이다.
보너스는 S, D, T 중 하나이다.
옵선은 *이나 # 중 하나이며, 없을 수도 있다.
{% endhighlight %}

<strong>출력 형식</strong>

{% highlight txt %}
3번의 기회에서 얻은 점수 합계에 해당하는 정수값을 출력한다.
예) 37
{% endhighlight %}

<strong>입출력 예제</strong>

| 예제 | dartResult | answer | 설명 |
| --- | --- | --- | --- |
| 1 | 1S2D*3T | 37 | $1^1$ * 2 + $2^2$ * 2 + $3^3$ |
| 2 | 1D2S#10S | 9 | $1^2$ + $2^1$ * (-1) + $10^1$ |
| 3 | 1D2S0T | 3 | $1^2$ + $2^1$ + $0^3$ |
| 4 | 1S*2T*3S | 23 | $1^1$ * 2 * 2 + $2^3$ * 2 + $3^1$ |
| 5 | 1D#2S*3S | 5 | $1^2$ * (-1) * 2 + $2^1$ * 2 + $3^1$ |
| 6 | 1T2D3D# | -4 | $1^3$ + $2^2$ + $3^2$ * (-1) |
| 7 | 1D2S3T* | 59 | $1^2$ + $2^1$ * 2 + $3^3$ * 2 |

{% highlight cpp %}
#include <string>
#include <vector>

using namespace std;

int solution(string dartResult) {
    vector<int> vi(3, 0);
    int n = 0, cnt = 0;
    
    for (decltype(dartResult.size()) i = 0; i != dartResult.size(); i++) {
        if (dartResult[i] >= 48 && dartResult[i] <= 57) {
            n += dartResult[i] - 48;
            if (dartResult[i + 1] >= 48 && dartResult[i + 1] <= 57) {
                n = n * 10 + dartResult[i++ + 1] - 48;
            } vi[cnt] = n;
            n = 0;
        } else if (dartResult[i] == '*') {
            vi[cnt - 1] *= 2;
            if (!cnt - 2) {
                vi[cnt - 2] *= 2;
            }
        } else if (dartResult[i] == '#') {
            vi[cnt - 1] *= -1;
        } else {
            if (dartResult[i] == 'D') {
                vi[cnt] *= vi[cnt];
            } else if (dartResult[i] == 'T') {
                vi[cnt] *= vi[cnt] * vi[cnt];
            } cnt++;
        }
    }
    
    for (auto i : vi) {
        n += i;
    } return n;
}
{% endhighlight %}
