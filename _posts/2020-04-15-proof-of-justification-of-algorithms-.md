---
layout: post
title:  "알고리즘의 정당성 증명"
date:   2020-04-15
excerpt: "이 알고리즘이 문제를 제대로 해결할 수 있을까?"
categories: 
 - Algorithms
tag:
 - algorithms
---

__이 글은 구종만님의 [알고리즘 문제해결 전략](https://www.aladin.co.kr/shop/wproduct.aspx?ItemId=21089176)를 공부하고 정리한 내용입니다. 필요한 부분만 발췌한 것으로 자세한 내용은 책을 참고해주시기 바랍니다. 또한, 개인적으로 편집하고 정리한 내용이므로 오류가 있을 수 있습니다.__

알고리즘의 증명을 공부해야 하는 이유는 많은 경우, 증명이 알고리즘을 유도하는 데 결정적인 통찰을 담고 있기 때문이다. 증명을 학습함으로써 알고리즘을 유도하는 중요한 깨달음을 얻을 수 있다.

## 수학적 귀납법과 반복문 불변식

### 수학적 귀납법
* 반복적인 구조를 갖는 명제들을 증명하는 데 유용하게 사용되는 증명 기법.

1. 단계 나누기  증명하고 싶은 사실을 여러 단계로 나눔. 대부분의 알고리즘은 어떤 형태로든 반복적인 요소를 가짐.
2. 첫 단계 증명  첫 단계에서 증명하고 싶은 내용이 성립함을 증명.
3. 귀납 증명  다음 단계에서도 성립함을 보임.

### 반복문 불변식
* 반복문의 내용이 한 번 실행될 때마다 중간 결과가 우리가 원하는 답으로 가는 길 위에 잘 있는지를 명시하는 조건.
* 반복문은 항상 이 식이 변하지 않고 성립해야 정당성이 있다고 증명할 수 있음.

1. 반복문 진입시에 불변식이 성립함을 보임.
2. 반복문 내용이 불변식을 깨뜨리지 않음을 보임.
    1. 반복문이 시작할 때, 불변식이 성립함을 보임.
    2. 내용이 끝날 때, 불변식이 항상 성립함을 보임.
3. 반복문 종료시, 불변식이 성립하면 항상 정답을 구했음을 보임.

```c++
// (*) 불변식은 여기에서 성립해야 함.
while(어떤 조건) {
    // 반복문 내용 시작
    ..
    //반복문 내용의 끝
    // (**) 불변식은 여기서도 성립해야 함.
}
```

## 귀류법
* 원하는 바와 반대되는 상황을 가정하고 논리를 전개해서 결론이 잘못됐음을 찾아내는 증명 기법.
* 귀납법과 귀류법을 모두 이용할 수 있음.
    * 알고리즘의 결과가 최선(최단 경로를 찾거나 가장 높은 탑을 쌓는 등)임을 보이기 위해 
    * 각 단계에서 최선의 선택을 함을 귀류법으로 증명하고
    * 각 단계에서 최선의 선택을 한다면 다음 단계에서도 최선의 선택을 할 수 있음을 증명.

---
* 구종만 저 [알고리즘 문제해결 전략](https://www.aladin.co.kr/shop/wproduct.aspx?ItemId=21089176)