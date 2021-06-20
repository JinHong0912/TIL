# [이론]🙋🏻‍♂️ 개념 : main() 메소드

날짜

@2021년 6월 20일

분야

JAVA 실습


# main() 메소드

-   main() 메소드, 커맨드라인 인수의 사용법

### 메인 메소드의 형식

-   main() 메소드는 프로그램을 실행할 때 최초로 호출되는 메소드로 하나의 클래스에 한개만 기술 할 수 있음.

```
1. 메소드의 수식자  2. 반환값의 형 3. 커맨드라인 인수

1. public static 2.void main(3.String[] args){

		메소드의 내용을 {} 안에 기술
}
```

### Ex

```
class Eat{

		void print1() {
	
			System.out.println("E");

		}

		void print2() {
	
			System.out.println("A");

		}

		void print3() {
	
			System.out.println("T");

		}

}

class Tea{

	public static void main(String[] args){ // 메인 메소드
	
		Eat eat = new Eat();

		eat.print3();
		eat.print1();	
		eat.print2();
	}
}
```

### 커맨드라인 인수 가져오기

-   main() 메소드의 인수는 String 클래스의 배열로 되어 있습니다.

-   인수는 커맨드라인으로 부터 입력을 받아 들입니다.

➡️

java Test(클래스 파일명) val1 val2 val3 = 커맨드라인 인수

```
class Main{

		public static void main(String[] args){
	
			int i;

			if(args.length == 0)
					System.out.println("커맨드라인 인수가 없습니다.");  <- 인수를 주지 않았을 때의 처리
		
			else for(i = 0; i < args.length; i++)
					System.out.println((i+1) +" : "+args[i])

		}
}
```

[![](%5B%E1%84%8B%E1%85%B5%E1%84%85%E1%85%A9%E1%86%AB%5D%20%E1%84%80%E1%85%A2%E1%84%82%E1%85%A7%E1%86%B7%20main()%20%E1%84%86%E1%85%A6%E1%84%89%E1%85%A9%E1%84%83%E1%85%B3%208d8470d1625543aba769f8b8330cba53/_2021-06-20__10.40.02.png)](%5B%E1%84%8B%E1%85%B5%E1%84%85%E1%85%A9%E1%86%AB%5D%20%E1%84%80%E1%85%A2%E1%84%82%E1%85%A7%E1%86%B7%20main()%20%E1%84%86%E1%85%A6%E1%84%89%E1%85%A9%E1%84%83%E1%85%B3%208d8470d1625543aba769f8b8330cba53/_2021-06-20__10.40.02.png)

### ✏️알게된 부분

-   main()의 이해

### 🙋🏻‍♂️참고 사이트

-   Java가 보이는 그림책

### 💦부족한 점

-   많이 보고 익히기
