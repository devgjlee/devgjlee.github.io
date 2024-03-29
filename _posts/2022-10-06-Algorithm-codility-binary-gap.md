---
title: '[Codility] Binary Gap - 이진 간격 구하기'
excerpt: 이진 간격 구하기
categories:
  - Algorithm
tags:
  - - Algorithm
    - Codility
toc: true
toc_sticky: true
date: 2022-10-06
last_modified_at: 2022-10-06
published: true
---



[문제]
양의 정수 N 내의 이진 간격 은 N의 이진 표현에서 양쪽 끝이 1로 둘러싸인 연속 0의 최대 시퀀스입니다.

예를 들어, 숫자 9는 이진 표현 1001 을 갖고 길이가 2인 이진 간격을 포함합니다. 숫자 529는 이진 표현이 1000010001 이고 두 개의 이진 간격(길이 4 중 하나와 길이 3 중 하나)을 포함합니다. 숫자 20은 이진 표현 10100 을 포함하고 다음을 포함합니다 . 길이가 1인 하나의 이진 간격. 숫자 15는 이진 표현 1111 을 가지며 이진 간격이 없습니다. 숫자 32는 이진 표현 100000 을 가지며 이진 간격이 없습니다.

함수 작성:

클래스 솔루션 { 공개 int 솔루션(int N); }

양의 정수 N이 주어지면 가장 긴 이진 간격의 길이를 반환합니다. N에 이진 간격이 포함되지 않은 경우 함수는 0을 반환해야 합니다.

예를 들어, N = 1041이 주어지면 함수는 5를 반환해야 합니다. N은 이진 표현이 10000010001 이고 가장 긴 이진 간격의 길이는 5이기 때문입니다. N = 32가 주어지면 함수는 0을 반환해야 합니다. N은 이진 표현이 '100000'이고 따라서 바이너리 갭이 없습니다.

다음 가정에 대한 효율적인 알고리즘을 작성 하십시오.

N은 [ 1 .. 2,147,483,647 ] 범위의 정수 입니다.

```java
class Solution {
    public int solution(int N) {
        char[] binaryN = Integer.toBinaryString(N).toCharArray();
        int cnt = 0;
        int max = 0;
        boolean flag = false;

        for(int i = 1 ; i < binaryN.length; i++) {
           if(binaryN[i] == '0') {
               cnt++;
           } else {
              max = Math.max(cnt, max);
              cnt =0 ;
           }
        }
        return max;
    }
}
```
