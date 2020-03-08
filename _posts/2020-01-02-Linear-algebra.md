---
title: "선형대수의 개념; <인공지능을 위한 선형대수> 정리"
classes: wide
categories:
  - Study
tags:
  - Math
  - Linear Algebra
author_profile : true
use_math : true
sidebar:
  - title: "Another Title"
    text: "More text here."
    nav: sidebar-sample
last_modified_at: 2020-01-02
---

#### **Linear Algebra** 선형대수

선형대수(線型代數)의 한자 의미를 살펴보면, 숫자(數)를 대신해서 선(線)의 형태(型)로 표현한다는 뜻을 가지고 있다. 즉, 어떤 함수가 선형(linear) 함수일 때 그 함수의 성질을 배우는 것으로, 벡터와 행렬을 주로 다룬다.

 

복잡한 비선형 문제를 간단한 선형 방정식으로 변환하여 문제를 해결할 수 있어, 자연과학과 물리학, 컴퓨터 그래픽 등의 다양한 분야에서 활용된다. 머신러닝에서는 PCA 등을 이용하여 차원(dimension)을 줄이거나, 학습(training)할 때 계산 과정을 줄이는 데 활용된다. 

 

#### **1. Linear Combination** 선형결합

> 주어진 벡터 v1, v2, ..., vn을 벡터공간 V의 벡터라고 할 때, 임의의 스칼라 k1, k2, ... , kn을 곱한 뒤 더한 것이다. 

#### **2. Span** 생성

영어 span은 (어떤 일이 지속되는) 기간 또는 (넓은 범위, 많은 것을) 포괄하다는 사전적 의미를 가지고 있다. 선형대수학에서도 '(어떤 공간을) 포괄한다'와 비슷한 의미를 지닌다. <코딩 더 매트릭스> 책에서는 Span을 다음과 같이 정의한다.

> 벡터들 v1, v2, v3, ..., vn 의 모든 선형결합으로 이루어진 집합을 이 벡터들의 생성(span)이라 하고, Span{v1, v2, v3, ... , vn} 라고 쓴다.



![img](https://k.kakaocdn.net/dn/cDNzQ5/btqzYLu45QV/TCKNEYkLtKzaafsPk04J51/img.png)Span의 수학적 정의



위키백과에서는 "어떤 벡터공간이 모든 부분공간의 교집합일 때, 그 벡터공간의 벡터의 집합이다. 고로 벡터들의 집합의 선형생성은 선형공간이다." 라고 설명한다. 도대체 무슨 말인지 모르겠다. 외계어같다.

 

다시 정리하면, 공집합이 아닌 집합 S의 span은 S의 원소들이 가능한 모든 선형결합의 집합이다. 예를 들어서, v1, v2, ..., vn 벡터들이 있을 때 벡터 간에 가능한 모든 선형결합으로 이루어지는 공간을 의미한다.

#### **3. Subspace** 부분공간

선형결합으로 이루어지는 공간이 원점을 지나고 덧셈 연산에 닫혀있는 경우, **부분 공간(subspace)**이 될 수도 있다.

> V와 W는 벡터공간이고, V가 W의 부분집합이면, V는 W의 부분공간(subspace)이라고 한다.

다시 정리하면, 벡터공간 V의 부분집합인 H가 다음을 만족할 때 부분공간(subspace)이라고 한다.

1. V에 속하는 영벡터(zero vector)가 H의 원소이다.
2. u,v∈H, u+v∈H,v+u∈H
3. u∈H이고 임의의 스칼라 c에 대해 cu∈H

부분공간의 기하학적 의미에 대한 설명은 [벡터공간, 부분공간, 열공간, 영공간](https://ratsgo.github.io/linear algebra/2017/05/20/spaces/) 글을 참고

 

**Subspace Example**

- {[0, 0]}은 자기 자신이 유일한 부분공간이 된다.
- 2차원에 포함된 벡터공간의 경우, 가장 작은 부분공간은 {[0, 0]}이며, 가장 큰 것은 2차원(R^2) 자기 자신이 된다. 
- 집합 R^2는 R^3에 포함되지 않기 때문에 R^3의 부분 공간이 아니다. 사실 R^2는 2-벡터들로 구성되고, R^3은 2-벡터들을 포함하지 않는다. 

#### **4. Basis** 기저

선형대수학에서 가장 중요한 개념 중 하나인 기저(basis)의 정의는 다음과 같다.

> V는 벡터공간이라 하자. V에 대한 기저(basis)는 V에 대한 생성자들로 구성된 선형독립(일차독립) 집합이다. 

간단하게 정리하면, 집합 S가 벡터공간 V를 표현할 수 있는 **최소한의 집합**이라면 S를 V의 기저라고 한다.

예를 들어서, 2차원 벡터공간 V의 기저는 [1, 0][0,1]이 된다. x, y 평면의 모든 벡터는 기저 벡터 [1, 0][0,1]를 변형하여 표현할 수 있기 때문이다. 그러나 벡터공간 V의 기저는 유일하지는 않다. 집합 S가 V의 기저일 때, **S의 모든 원소에 임의의 상수를 곱하여도 기저의 조건을 만족**하기 때문이다. 

 

**Basis 성질**

따라서 V의 벡터들의 집합 B는 만약 B가 다음 두 성질을 만족하면 V에 대한 기저이다. 

1. (Spanning) Span B = V이다.
2. (Independent) B는 선형독립이다.

다시 정리하면,

1. 기저 벡터들은 공간(space)을 생성(span) 한다.
2. 기저 벡터들은 선형독립(independent)이다.

기저와 함께 나오는 개념인 **차원(dimension)**은 기저 벡터의 개수를 의미한다. 차원의 기호는 dim(*V*)로 표현한다.

 

**Dimension 특징**

1. 벡터공간 V의 기저 B를 구성하는 원소의 개수를 V의 차원이라고 한다.
2. 차원이 유한한 벡터공간을 '유한 차원 벡터공간'이라 한다.
3. 차원이 무한한 벡터공간을 '무한 차원 벡터공간'이라 한다.

따라서 1차원은 선으로 이루어져 있다. 2차원은 x축과 y축의 기저로 이루어진 벡터 공간이며, 3차원은 x축, y축, z축의 세 기저로 이루어진 벡터 공간이다.

#### **5. Determinant** 행렬식

행렬식(determinant)은 정사각행렬의 계산식에 수를 대입하여 얻는 함수이며, 행렬이 아니다. 역행렬과 마찬가지로 정방 행렬(square matrix)에서만 정의된다. 행렬식은 결정 요인(determinant)이라는 뜻처럼 행렬의 특성 중 하나인 역행렬 존재 여부를 판별할 수 있다.

 

**행렬식의 기하학적 의미**

2차 정사각행렬의 행렬식 절대값은 두 벡터로 이루어진 평행사변형의 넓이와 같다. 3차 정사각행렬 행렬식의 절대값은 세 벡터로 이루어진 평행육면체의 부피와 같다. 정리하면, 좌표 평면에 있는 어떤 도형을 행렬로 1차 변환할 때, 변환한 도형의 넓이는 변환 전의 넓이의 절대값을 곱한 것과 같다.

 

**행렬식의 성질**

- det(A) = ad-bc
- det(AB)=det(A)det(B)

 