---
title: "[자료구조]1.1 Introductions to Data Structure"
excerpt: "자료구조 정리를 시작하며"
categories: #카테고리
  - data-structure
tags: # 태그 사용
  - data-structure
  - introductions
author_profile: true #작성자 프로필 출력 여부
read_time: false #read_time을 출력할지 여부 1min read 같은 것

toc: true #Table Of Contents 목차 보여줌
#toc_table: "Contents" #toc 이름 정의
toc_icon: "file-alt" #font Awesome 아이콘으로 toc 아이콘 설정
toc_sticky: true # 스크롤 내릴때 같이 내려가는 목차


header: #헤더에 유투브 비디오 삽입
video:
 id:
 provider:

#link: https://github.com #direct link 만들

last_modified_at: 2019-01-24T02:00:00+09:00
---

### Intro
자료구조 (data structure) 란?

자료(data)를 다루는 여러가지 방법을 의미합니다.  
자료형에 따른 분류는 다음과 같습니다.
![자료구조-분류](/assets/images/data-structure/_01/_01-data-structure.png)  
[(출처:cse-tutor)](https://www.csetutor.com/classification-of-data-structure-with-diagram/)  

{% capture intro %}

- Primitive Data Structure (원시 자료구조)
: 프로그래밍 언어에 따라 다르나, 자료를 구성하는 가장 기본적인 단위입니다.  

  - Integer (정수형)
  : 수학의 '정수'에 해당하는 단위입니다.  
    단, 수학에서 다루는 '정수' 범위와 달리, 유한한 범위를 갖습니다.  
    유한한 범위는 프로그래밍 언어에 따라 약간씩 다릅니다.  
    불리는 이름도 약간씩 차이가 있습니다.  

  - Float (실수형)
  : 수학의 '실수'에 해당하는 단위입니다.  
    실수 범위에는 유리수(rational number)와 무리수(irrational number)가
    포함됩니다.  
    단, 정수형과 마찬가지로 컴퓨터에서는 표현 범위가 한정적이므로,    
    정확한 소수점 아래 값을 나타낼 수 없습니다.  
    따라서, 소수점 몇 번째 자리까지 나타낼 수 있는지가  
    실수형의 범위가 됩니다.   
    이 부분에 대해서는 추후 포스팅에서 설명하도록 하겠습니다.  

  - Character (문자)
  : 문자는 말 그대로 하나의 문자를 뜻합니다.
    이 때 문자는 a,T,^ 와 같이 보이는 문자 뿐만 아니라  
    띄어쓰기, tab, enter와 같은 공백문자(white space)도 포함합니다.  

  - Pointer (포인터)
  : 포인터는 Integer나 Float, Character 처럼  
    그 자체로 의미있는 값을 갖지 않습니다.  
    대신에 자료형이 컴퓨터 메모리 내에서 저장된 곳,  
    즉, 메모리 내의 주소를 통해 자료형의 실제 값을 불러낼 수 있습니다.  
    이 부분 또한 추후 포스팅에서 설명하도록 하겠습니다.

- Non-Primitive Data Structure (비원시 자료구조)
: 프로그래밍 언어에 따라 다르나, 주로 원시 자료구조를 응용한 자료구조입니다.

  - Arrays (배열)
  : 자료형을 원소로 취급해 나열한 것입니다.  
    원소번호인 인덱스(index)를 통해 빠른 접근이 가능합니다.  
    기본적으로는 갯수(크기)가 정해져 있습니다.  
    갯수가 정해진 자료를 다룰 때에 유용합니다.  

  - Lists (리스트)
  : 하나의 자료가 다른 자료를 가리키며 자료들을 축적해나가는 구조입니다.  
    갯수가 정해져 있지 않은 자료들을 다룰 때에 유용합니다.  
    따라서 배열에 비해 불필요한 빈 공간을 낭비하지 않습니다.  
    단, 인덱스(index)가 없으므로,  
    접근시 배열과 달리 한 번에 찾기가 어렵습니다.

    - Linear Lists (선형 자료구조)
    : 자료가 순서대로 나열된 구조입니다. 즉 순서를 갖는 자료구조입니다.
      - Stack (스택)  
      : LIFO(Last In First Out) 형식을 갖는 구조입니다.   
        다시 말해 맨 마지막에 들어간 자료가 가장 먼저 연산 대상이 됩니다.  
        C언어 프로그램에서 함수 호출시 스택 자료구조를 사용합니다.  

        - Queue (큐)  
        : FIFO(First In First Out) 형식을 갖는 구조입니다.  
          다시 말해 맨 처음에 들어간 자료가 가장 먼저 연산 대상이 됩니다.  
          프린터기와 같이 먼저 들어온 자료에 대한 수행이 이뤄지도록 합니다.  
    - Non Linear Lists (비선형 자료구조)
    : 자료의 순서가 정해져 있지 않은 구조입니다.
      - Graph (그래프)  
      : 그래프는 vertex(점) V와 edge(모서리) E로 구성된 집합입니다.
        이 때, 그래프는 방향성을 갖는 방향 그래프와 무방향 그래프로 나뉩니다.
        주로 자료와 자료사이의 관계를 나타낼 때 사용합니다.  

      - Tree (트리)
      :
  - Files (파일)

{% capture intro %}
<div class="notice--primary">{{ intro | markdownify }}</div>

---
### Description



---
### 이 글을 마치며
