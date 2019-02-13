---
title: "[자료구조]1.2 Primitive Type: Integer (2) 범위와 명칭"
excerpt: "Integer(정수형)의 범위와 표현 가능한 크기에 대하여"
categories: #카테고리
  - datastructure
tags: # 태그 사용
  - datastructure
  - Integer
  - Fundamental-type
  - primitive-datatype
  - 정수형
  - 기본자료형
  - range
  - boundary
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
  image:
  teaser: /assets/images/teasers/teaser_12.jpeg #티저이미지

#link: https://github.com #direct link 만들

last_modified_at: 2019-02-13T15:00:00+09:00
---

## Intro
지난 포스팅에서는 컴퓨터가 어떻게 정수를 처리하는지에 대해,  
특히 음수를 처리하는 방법에 대해 알아보았습니다.  
이번 포스팅에서는 정수형의 범위와 표현 가능한 크기를 함께 알아보겠습니다.  

{% capture intro %}
<b>signed 와 unsigned?</b>  
이전 포스팅에서 다루었듯이 MSB(최상위 부호 비트)를 부호비트로 사용할 경우  
이를 signed라고 하고, 기본 데이터형이 signed에 속한다고 하였습니다.  
unsigned는 말 그대로 signed가 아니므로, MSB까지 데이터를 나타내는 비트로 사용합니다.  
단, unsigned 데이터형에서는 음수를 구분할 방법이 없으므로,  
signed에서 표현한 음수 범위만큼 양수 표현 범위가 늘어나게 됩니다.  
 <img src="/assets/images/datastructure/integer/data-structure-range-04.png" width="240" height="200">  
※ <b>주의! Java에서는 primitive type에서 unsigned 개념이 존재하지 않음.</b>   
{% endcapture %}
<div class="notice--primary">{{ intro | markdownify }}</div>

## Description

정수형의 범위는 언어별로 약간의 차이가 있습니다.  
C, C++, Java의 경우를 살펴보겠습니다.  

### Integers in C language (& C++ language)  
C언어와 C++언어에서 정수형으로 나타낼 수 있는 범위와 명칭은 거의 같습니다.  
<a href="https://en.cppreference.com/w/cpp/language/types" style="float: right" target="_blank">(참고: cppreference-fundamental-type)</a>
<br>
![datastructure_06](/assets/images/datastructure/integer/data-structure-range-c-cplusplus.png)  

### Integers in Java (Primitive Type)  
Java의 경우는 정수형으로 나타낼 수 있는 범위가 4가지로 한정됩니다.  
또한, 위에서 언급한대로 기본 타입에서 unsigned는 존재하지 않습니다.  
단, 굳이 사용할 경우 Java에서 제공하는 Wrapper Class 내의 함수(<u><b>JAVASE 8 이상</b></u>)를 이용해 값을 변환할 수 있습니다.  
<a href="https://docs.oracle.com/javase/10/docs/api/java/lang/Integer.html  
" target="_blank" style="float: right;">(참고: Javase8 Docs-Java.lang.Integer)</a>  


![datastructure_07](/assets/images/datastructure/integer/data-structure-range-java.png)  

<details>
  <summary>Java에서 Unsigned 형 integer를 사용하는 방법 [클릭]</summary>  
  <p>
  {% highlight java %}
  import java.lang.*;

public class unsigned_integer_test {

	public static void main(String[] args) {

		byte leastByte = Byte.MIN_VALUE;
		System.out.println(leastByte);
		System.out.println(Byte.toUnsignedInt(leastByte));

		short leastShort = Short.MIN_VALUE;
		System.out.println(leastShort);
		System.out.println(Short.toUnsignedInt(leastShort));

		int leastInt = Integer.MIN_VALUE;
		System.out.println(leastInt);
		System.out.println(Integer.toUnsignedLong(leastInt));

		long leastLong = Long.MIN_VALUE;
		System.out.println(leastLong);
		System.out.println(Long.toUnsignedString(leastLong));
	}

}
  {% endhighlight %}
  <br>
  <b>출력 화면</b>
  {% capture unsigned-in-java %}
  -128  
  128  
  -32768  
  32768  
  -2147483648  
  2147483648  
  -9223372036854775808  
  9223372036854775808  
  {% endcapture %}  
  <div class="notice--primary">{{ unsigned-in-java | markdownify }}</div>

  {% capture unsigned-string %}  
  <b>toUnsigned~ 함수로 Unsigned type이 만들어지는 건가요?</b>  

  아닙니다.  
  Unsigned type을 따로 만들어 주는 것이 아니라, 해당 데이터형보다 더 넓은 범위의 데이터형으로 바꾸어주는 함수입니다.  
  엄밀히 말하면 형변환을 시켜주는 함수라고 볼 수 있습니다.   
  byte  → toUnsignedInt()     → int  
  short → toUnsignedInt()     → int  
  int   → toUnsignedLong()    → Long  
  long  → toUnsignedString()  → String  
  단, 맨마지막의 toUnsignedString()함수를 통해 변환된 값은 정수형이 아닌 <u><b>String type</b></u>이므로 primitive type이 아닙니다.  
  <a href="https://docs.oracle.com/javase/8/docs/api/java/lang/Byte.html" style="float: right;" target="_blank">(참고: Javase8 Docs:Byte)</a>  
  <br>
  {% endcapture %}
  <div class="notice--warning">{{ unsigned-string | markdownify }}</div>
  </p>
</details>  


## Summary
이번 포스팅에서는 정수형이 표현할 수 있는 범위와, 그 명칭에 대해서 살펴보았습니다.  
하지만, 안타깝게도 이 기본형이 무조건 적용되는 것은 아닙니다.  

C언어와 C++언어에서는 사용자의 PC의 CPU의 bit수에 따라 범위가 달라질 수 있습니다.  
또한, 특정 라이브러리를 통해 데이터형의 byte수를 조정하여  
기본 데이터형에서 수용할수 있는 범위를 넓히거나 좁힐 수 있습니다.  
<a href="https://en.cppreference.com/w/cpp/language/types" style="float: right" target="_blank">(참고: cppreference-fundamental-type)</a>
<br>

이 외에도 많은 프로그래밍 언어에서 정수형을 범위에 따라 다루고 있습니다.   

Swift - [(참고: Swift Docs org)](https://docs.swift.org/swift-book/LanguageGuide/TheBasics.html)  
C#    - [(참고: Microsoft C# .NET Docs)](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/integral-types-table)  

단, python 버전 3 이상부터는 순수 int는 범위 변경이 다소 자유로운 편입니다.  
Python 3.x - [(참고: Python Docs org)](https://docs.python.org/3.7/library/stdtypes.html?highlight=integer)

범위와 연결된 <b><u>overflow</u></b>는 다른 기본자료형 포스팅이 끝나는대로 상세히 설명하겠습니다.  

감사합니다.  
