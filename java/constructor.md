# [이론]🙋🏻‍♂️ 개념 : 생성자

날짜 : @2021년 6월 20일
분야 : JAVA 실습
### 🙋🏻‍♂️이론 내용

# 생성자

-   오브젝트 생성할 때 호출되는 생성자를 말한다.

### 생성자란?

-   생성자란 오브젝트 생성과 함께 자동적으로 호출되는 특수한 메소드이다.

### 인수가 없는 생성자

```
class A{

	int a, b, c ;

	A() { // 클래스와 같은 이름
		
		 a = 0;
		 b = 0;   생성자
		 c = 0;
	}
}

class TestA {
	
	A a = new A() ; <- 오브젝트의 생성 = 생성자의 호출
	
}

# 필드를 초기화할 떼 등에 이용 할 수 있다.
```

### 인수가 있는 생성자

```
class B{

	int s, t ;

	B(int a , int b) {
			s = a;
			t = b;     생성자
	}
}

class TestB{
		B b = new B(3,4);
}
```

### Ex

```
class Book{
	
		int price;
		int num = 0;
		String title;
	
		Book(String t, int p){
	
			title = t;
			price = p;
				
		}
		void print(){
				
			System.out.println("제   목 : " + title);
			System.out.println("가   격 : " + price);
			System.out.println("주문수량 : " + num);
			System.out.println("합계금약 : " + price * num);
		}	
}

class Books{
	
		public static void main(String[] args){

		Book book = new Book("C가 보이는 그림책", 12000);
		
		book.num = 10;
		book.print();

		}


}

```

### 결과

[![](%5B%E1%84%8B%E1%85%B5%E1%84%85%E1%85%A9%E1%86%AB%5D%20%E1%84%80%E1%85%A2%E1%84%82%E1%85%A7%E1%86%B7%20%E1%84%89%E1%85%A2%E1%86%BC%E1%84%89%E1%85%A5%E1%86%BC%E1%84%8C%E1%85%A1%2059afa049df844011b7ad4df6549a6313/_2021-06-20__9.31.48.png)](%5B%E1%84%8B%E1%85%B5%E1%84%85%E1%85%A9%E1%86%AB%5D%20%E1%84%80%E1%85%A2%E1%84%82%E1%85%A7%E1%86%B7%20%E1%84%89%E1%85%A2%E1%86%BC%E1%84%89%E1%85%A5%E1%86%BC%E1%84%8C%E1%85%A1%2059afa049df844011b7ad4df6549a6313/_2021-06-20__9.31.48.png)

# 여러 가지 생성자

-   디폴트 생성자와 복제 생성자

### 디폴트 생성자

-   생성자를 기술하지 않은 경우, 인수가 없는 생성자가 자동으로 만들어진다.이것이 디폴트 생성자 이다. 컴파일하는 과정에서 자동으로 만들어 준다

```
class Bool{

		Book(){ 디폴트 생성자        
		                          
		}                         
}
```

### 복제 생성자

-   동일한 클래스의 오브젝트를 인수를 받아서, 대응하는 필드에 값을 대입하는 생성자를 복제 생성자라고 함.

-   복제 생성자는 전달 받은 오브젝트를 복제 한다.

```
class Book {

	BooK(Book copy){ // Book(클래스명 변수명)
		title  = copy.title;  
		writer = copy.writer;    복제 생성자
		price  = copy.price;
	}
}

class Books{

		Book book2 = new Book(book1)	

}
```

### Ex

```
class Book {

	String title;
	String writer;

	Book(String t, String w){
		title  = t;
		writer = w;
	}

	Book (Book copy) {
		title  = copy.title;
		writer = copy.writer;
	}

	void print(){
				
			System.out.println("제  목 : " + title);
			System.out.println("저  자 : " + writer); 

	}
}

class Books {

		public static void main(String[] args){

			Book book1 = new Book("C 가 보이는 그림책" , "ANK");
			book1.print();

			Book book2 = new BooK(book1);
			book2.title = "Java가 보이는 그램책";
			book2.print();

		}

}

```

### 결과

[![](%5B%E1%84%8B%E1%85%B5%E1%84%85%E1%85%A9%E1%86%AB%5D%20%E1%84%80%E1%85%A2%E1%84%82%E1%85%A7%E1%86%B7%20%E1%84%89%E1%85%A2%E1%86%BC%E1%84%89%E1%85%A5%E1%86%BC%E1%84%8C%E1%85%A1%2059afa049df844011b7ad4df6549a6313/_2021-06-20__10.02.07.png)](%5B%E1%84%8B%E1%85%B5%E1%84%85%E1%85%A9%E1%86%AB%5D%20%E1%84%80%E1%85%A2%E1%84%82%E1%85%A7%E1%86%B7%20%E1%84%89%E1%85%A2%E1%86%BC%E1%84%89%E1%85%A5%E1%86%BC%E1%84%8C%E1%85%A1%2059afa049df844011b7ad4df6549a6313/_2021-06-20__10.02.07.png)

### ✏️알게된 부분

-   복제 생성자도 사용 가능 하다는 것을 알게됨

### 🙋🏻‍♂️참고 사이트

-   Java가 보이는 그림책

### 💦부족한 점

-   실습 계속 해서 익히기


