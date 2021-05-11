# 🙋🏻‍♂️[이론] @RequestBody와 @ResponseBody 사용


### 🙋🏻‍♂️이론 내용


**💡 이번에는 @RequestBody와 @ResponseBody를 왜 사용 하는지 알아 보자.**

### 서론

스프링에서 비동기 처리를 하는 경우 @RequestBody 와 @ResponseBody를 사용 한다.

실제로 프로그램을 할때 위의 어노테이션을 사용 하여 어떻게 비동기 처리를 할 것인지를 알아보자

### 클라이언트와 서버의 비동기 통신 처리

웹에서 이루어지는 데이터를 가져오고, 전송하는 이러한 동작들은 `클라이언트(Client)와 서버(Server)간의 통신`이 이루어지기 때문에 가능하다.

EX) 우리가 브라우저에서 검색 키워드를 입력하고 검색 버튼을 누르게 되면 검색 키워드가 클라이언트(JS)를 통해 서버(Java)로 전송이 되면 서버에서 검색 키워드를 이용하여, 클라이언트에서 요청한 메시지를 처리하고, 응답을 만들어서 다시 클라이언트로 보내며 클라이언트는 화면에 뿌리는 역할을 하게 된다.

여기서 중요한 포인트가 바로 `요청(Request)` 과 `응답(Response)` 이다.

즉, 클라이언트에서 서버로 통신하는 메시지를 요청메시지라고 하며, 서버에서 클라이언트로 통신하는 메시지를 응답 메시지라고 한다.

더 자세히 배우고 싶다면 [🙋🏻‍♂️[이론] HTTP : Request , Response 개념공부](https://www.notion.so/HTTP-Request-Response-d99e816b0bcb4cbb9a82918250a61b25)

보통 웹에서 화면 전환( refresh, F5)이 없이 이루어지는 동작들은 대부분 비동기 통신으로 이루어진다. 비동기 통신을 하기 위해서 클라이언트가 서버로 요청 메시지의 본문에 데이터를 담아서 보내야 하며, 서버도 클라이언트로 응답을 보내기 위해서는 응답 메시지에 본문에 데이터를 담아서 보내야한다.

중요한 포인트는 바로 `본문(Body)`이다. 위와 같이 강조한 포인트 `요청(Request)과 응답(Response)` 그리고 다음으로 강조한 포인트인 본문을 연결하여 단어를 만들면

`요청본문(RequestBody),응답본문(ResponseBody)` 라는 단어가 만들어진다.

여기서 본문에 담겨야 하는 데이터의 형식은 무엇일까?

여러 종류가 있겠지만 대표적으로 사용 되는 것은 바로 JSON(Javascript Object Notation)이다.

> JSON(제이슨, JavaScript Object Notation)은 속성-값 쌍 또는 키-값으로 이루어진 데이터 오브젝트를 전달하기 위해 인간이 읽을 수 있는 텍스트를 사용하는 개방형 표준 포맷이다. 비동기 브라우저/서버 통신(AJAX)을 위해, 넓게는 XML(AJAX가 사용)을 대체하는 주요 데이터 포맷이다. 특히, 인터넷에서 자료를 주고 받을 때 그 자료를 표현하는 방법으로 알려져 있다. 자료의 종류에 큰 제한은 없으며, 특히 컴퓨터 프로그램의 변수 값을 표현하는데 적합

### 즉, 비동기 클라이언트 서버 통신을 위해서 데이터를 전송하는데 JSON이라는 형식의 데이터를 서버와 클라이언트 서로서로에게 전송하는 것.

----------

### 요청 본문(@RequestBody)에 담긴 값을 자바 객체로 Conversion

@RequestBody를 통해서 자바 객체로 `Conversion` 을 할 때 그냥 변환되는 것이 아니라 `HttpMessageConverter` 를 사용하는데 아래의 메서드에 각종의 메시지 `Converter(컨버터)`가 설정 되어 있다.

```
WebMvcConfigurationSupport.addDefaultHttpMessageConverters
```

만약 요청이 JSON으로 들어온 경우 요청 헤더에(Request header)에 컨텐츠타입(Content-Type)을 알려줘야 한다. 그러면 헤더에 있는 컨텐츠 타입을 보고 JSON을 컨버팅 할 수 있는 컨버터`(Jackson20bjectMapperBuilder)`를 사용 해야 겠다라고 JSON을 자바 객체러 변환하는 메시지 컨버터를 사용하여 요청 본문에 담긴 데이터를 자바 객체로 변환 하게 되는 것이다.

```
@RestController
@RequestMapping("/api")
public class HttpMessageController {

  /**
  * @RequestBody를 통해 자바 객체로 변환할 때 HttpMessageConverter를 사용하여 
  * 헤더에 담긴 컨텐츠 타입을 보고 어떤 메시지 컨버터를 사용할 것인지 판단하여 
  * 요청 본문에 담긴 값을 자바 객체로 변환
  */
  @GetMapping
  public String create(@ReqeustBody Event event) {
    // 생략
    return "redirect:/api/list";
  }
  
}

참고 :
HttpMessageConvertersExample.java hosted with ❤ by GitHub
```

`Jackson20bjectMapperBuilder` 는 스프링 부트에서 `JacksonAutoConfiguration` 클래스에서 자동으로 설정하기 때문에 별다른 설정없이 JSON을 자바 객체로 변환하는 `ObjectMapper` 를 사용 할 수 있다.

`Jackson20bjeckMapperBuilder` 내부를 보면 **autoDetectGettersSetters()라는 메서드를 사용 한다.**

즉, JSON 타입으로 변환하기 위한 객체(DTO)에 getter 와 setter 메서드가 존재 해야 한다는 뜻

```
public Jackson2ObjectMapperBuilder autoDetectGettersSetters(boolean autoDetectGettersSetters) {
    this.features.put(MapperFeature.AUTO_DETECT_GETTERS, autoDetectGettersSetters);
    this.features.put(MapperFeature.AUTO_DETECT_SETTERS, autoDetectGettersSetters);
    this.features.put(MapperFeature.AUTO_DETECT_IS_GETTERS, autoDetectGettersSetters);
    return this;
}

참고 :
Jackson2ObjectMapperBuilder.java hosted with ❤ by GitHub
```

만약 getter/setter가 존재하지 않으면 응답 메시지를 내보낼때 `Jackson20bjectMapperBuilder`를 제대로 사용하지 못해서 JSON 타입으로 변환이 제대로 되지 않아 클라이언트(JS) 단에서 success() 함수로 결과값(res)를 받아 올 수 없다.

```
@RequriedArgsConstructor
@RequestMapping("/test")
@RestController
public class RequestBodyTestController {

  private final TestService testService;

  /**
   * TestDto 에 getter, setter 메서드가 없으면
   * JSON 타입 변환에 실패하여 JS 의 success 함수가 아닌 error 함수를 타게 된다.
   */
  @RequestMapping("/search")
  public TestDto search(TestVo testVo) {
    TestVo result = testService.findTest(testVo);
    return result.toDto();
  }

}
참고 :
RequestBodyTestController.java hosted with ❤ by GitHub
```

스프링부트의 pom.xml 을 보면 `spring-boot-starter-web` 이 존재하는데 내부에 들어가보면

`jackson-databind`의존성이 자동으로 잡혀있는 것을 볼 수 있다. 해당 의존성이 있어야 JSON타입으로 제대로 변환이 된다.

## 정리

클라이언트에서 서버로 필요한 데이터를 전송하기 위해서 JSON이라는 데이터를 요청 본문(RequesrBody)에 담아서 서버로 보내면, 서버에서는 **@RequestBody** 어노테이션을 사용하여 `HTTP요청 본문에 담긴 값들을 자바 객체로 변환` 시켜, 객체에 저장시킨다.

서버에서 클라이언트로 응답 데이터를 전송하기 위해서 **@ResponseBody** 어노테이션을 사용하여 `자바 객체를 HTTP 응답 본문(ResponseBody)의 객체로 변환` 하여 클라이언트로 전송시키는 역활을 한다.

### ✏️알게된 부분

-   요청 본문(RequestBody) 와 응답 본문(ResponseBody) 에 대한 개념을 잡게 되었다

### 🙋🏻‍♂️참고 사이트

[](https://webdevtechblog.com/reqeustbody%EC%99%80-responsebody-%EC%96%B8%EC%A0%9C-%EC%82%AC%EC%9A%A9%ED%95%A0%EA%B9%8C-2efcab364edb)

@ReqeustBody와 @ResponseBody 언제 사용할까?

스프링에서 비동기 처리를 하는 경우 @RequestBody 와 @ReponseBody 를 사용합니다. 여기서는 좀 더 자세하게, 위 어노테이션을 사용하여 어떻게 비동기 처리를 할 것인지에 대해서 배워보겠습니다. 예를들어 우리가 브라우저에서 검색 키워드를 입력하고 검색 버튼을 누르게 되면 검색 키워드가 클라이언트(ex. Js)를 통해 서버(ex...

![](https://miro.medium.com/1*m-R_BkNf1Qjr1YbyOIJY2w.png)https://webdevtechblog.com/reqeustbody%EC%99%80-responsebody-%EC%96%B8%EC%A0%9C-%EC%82%AC%EC%9A%A9%ED%95%A0%EA%B9%8C-2efcab364edb

![](https://miro.medium.com/max/765/1*J0POP1cMlf52jAfjuxX5sg.jpeg)

→ 위에 사이트에서 내용을 보고 직접 타이핑으로 작성

### 💦부족한 점

-   개념을 튼튼히 해야 겠다.


