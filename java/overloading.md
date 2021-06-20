
# [이론]🙋🏻‍♂️ 개념 : 오버로딩

날짜

@2021년 6월 20일

분야

JAVA

### 🙋🏻‍♂️이론 내용

# 오버로딩

### 오버로딩이란?

-   오버로딩이란 하나의 클래스 내에 인수의 개수나 형이 다른 동일한 이름의 메소드를 여러개 정의 하는 것

```
class Calc {

		int add(int a, int b){
			return a + b;
		}
		
		int add(int a){
			return a + 1;
		}

		int add(double a , double b){
			return a + b;
		}

}
```

### 오버로딩된 메소드 호출하기

-   메소드를 호출할 때 주어진 인수에 의해 인수의 수와 형이 일치하는 메소드가 호출된다.

-   동일한 이름의 메소드라도 인수의 개수와 형이 다르다.

```
class Cat{
	String name;
	String place;
	int age;

	void setData(String n,String p ,int a){

		name  = n;
		place = p;
		age   = a;

	}
	//1
	void print(){
		
		System.out.println(place + ":" + name + "  " + age + "살");

	}
	//2
	void print( String p , int a ){
		
		place = p;
		System.out.println(place +": 고양이는  "+ a + "마리입니다.");
	}

	//3
	void print(String variety){
		
		System.out.println(place +":"+name+"  "+ age +"세"+ variety);


	}

}

class Pet{

		public static void main(String[] args){
			
		Cat cat1 = new Cat();
		Cat cat2 = new Cat();
		Cat cat3 = new Cat();
		
		cat1.setData("로빈" , "우리집" , 10);
		cat2.setData("아이" , "옆 집" , 14 );

		cat1.print("잡종");//3
		cat2.print();//1
		cat3.print("우리집" , 0);//2

		}



}
```

### 결과

[![](%5B%E1%84%8B%E1%85%B5%E1%84%85%E1%85%A9%E1%86%AB%5D%20%E1%84%80%E1%85%A2%E1%84%82%E1%85%A7%E1%86%B7%20%E1%84%8B%E1%85%A9%E1%84%87%E1%85%A5%E1%84%85%E1%85%A9%E1%84%83%E1%85%B5%E1%86%BC%20390784a2b16942b48c78ce8f354d3f25/_2021-06-20__7.01.13.png)](%5B%E1%84%8B%E1%85%B5%E1%84%85%E1%85%A9%E1%86%AB%5D%20%E1%84%80%E1%85%A2%E1%84%82%E1%85%A7%E1%86%B7%20%E1%84%8B%E1%85%A9%E1%84%87%E1%85%A5%E1%84%85%E1%85%A9%E1%84%83%E1%85%B5%E1%86%BC%20390784a2b16942b48c78ce8f354d3f25/_2021-06-20__7.01.13.png)

### ✏️알게된 부분

-   정확하게 이해 하지 못한 부분 확인 함

### 🙋🏻‍♂️참고 사이트

-   Java가 보이는 그림책

### 💦부족한 점

-   실습을 해보고 타이핑으로 정확하게 확인

-   오버로딩이 무엇인지 확인!!
