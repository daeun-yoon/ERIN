---
title: 200107_TIL_Data Sturcture
date: "2020-01-07T22:40:32.169Z"
template: "post"
draft: false
slug: "/posts/sturcture1"
category: "TIL"
description: "array, tuple, set"
tags:
  - "TIL"
  - "자료구조"
  - "Data"
  - "Data Sturcuture"
---

# Data Sturcture(자료 구조)

![image.png](https://images.velog.io/post-images/jotang/98ff2bc0-31db-11ea-b5c5-2f2d7a673cc4/image.png)

- 자료구조 란 데이터에 편리하게 접근하고, 변경하기 위해서 데이터를 **저장하거나 조직하는 방법**
- 데이터를 무엇을 할것인지에 따라
- 어떤 자료구조를 선택하느냐에 따라 코드의 가독성 등 이 달라지게 된다.

- Primitive Data Structure(단순구조): 프로그래밍에서 사용되는 기본 데이터 타입

## Non-Primtive Data Sturcture(비단순 구조)

- 단순한 데이터를 저장하는 구조가 아니라 여러 데이터를 목적에 맞게 효과적으로 저장하는 자료 구조.

## Linear

- Data Structure(선형구조): 저장되는 자료의 전후관계가 1:1 (리스트, 스택, 큐 등)
- Non-Linear Data Structure(비선형구조): 데이터 항목 사이의 관계가 1:n 또는 n:m (트리, 그래프 등)

# 1.Array

- 말그대로 나열된채로 저장하는 것

```
[0,1,2,3,4,5,6]
```

## 특징

- 순서가 있음(실제 메모리상에서 순서대로 옆으로 저장된다)
- 순서가 있으니 index가 있다.
- index가 있기때문에 찾아서 쓸 수 있다.
- slice가 가능(잘라내기)
- array 안에 array도 가능하다. (다차원array)

## 단점

- 연차적으로 저장되야한다.
- 연속적으로 이어져있는 저장공간이 미리 확보되어있다.
- resizing의 문제가 있다.

![image.png](https://images.velog.io/post-images/jotang/8ae29fb0-31de-11ea-bbeb-970b96b1b861/image.png)

- 중간중간 지우는 일에도 비효율적이다.
- array의 앞으로 추가하는 일도 비효율적이다.

## 이럴때 사용하세요

- 순차열적인 데이터를 저장할때
- 어떠한 특정 요소를 빠르게 읽어야 할때
- 데이터의 사이즈가 급변하게 자주 변하지 않을때
- 그리고 요소를 자주 삭제해야 하지 않을때

## array 사용의 적절한 예

- 학교 애들 번호
- 등수( 1등이 누구인지 바뀔수는 있지만, 1,2,3이 바뀌지 않는다)
- 주식데이터

# 2.Tuple

## 특정

- array이와 마찬가지로 순차적으로 저장
- 대신, 값을 바꿀 수 없다.(수정할수없음)
- 소규모 데이터를 저장할 때 쓴다.

* ex> 좌표

```
coordinations = [
    (1, 2),
    (3, 4),
    (5, 6)
]
```

- class 등으로 표현할 수 는 있지만 비효율적이다.
- 메모리가 array보다 효율적이다.

# 3.Set

- array 처럼 순열 자료구조
- set는 순서가 없다.
- index가 없다
- 중복된 값은 허용되지 않는다.

* ex> 마니또~~!, 주민번호, 자동차번호판, 전화번호

## 순서가 없는 이유??

- 1을 저장할 때 단방향 hash를 적용, 그 값에 해당하는 메모리에 1을 저장, 2을 저장할 때 단방향 hash를 적용, 그 값에 해당하는 메모리에 2을 저장
- 같은 1을 저장할 때는 똑같은 hash값이 나오고 그 hash값에 해당되는 메모리에 저장되기 때문에 중복이 허용되지 않게 된다.
- hash값에 해당하는 메모리가 다 세팅되어있나?? set는 결국에 array에 저장되는 느낌쓰
- set이 되는 순간 array처럼 저장공간이 마련이 되고,
- 충돌이나면 다른 곳으로 옮긴다.
- 헤쉬의 비트를 4개씩 떼가면서 나누기??
- 특정값을 찾는데 편하다.
- look up이 빠르다.