# String, StringBuilder, StringBuffer의 차이점  

## String 
String은 불변객체로, + 연산자를 활용하여 문자열을 결합하면 내용이 합쳐진 새로운 String 인스턴스를 생성해 공간을 낭비하고 속도 또한 느려지게 된다.

```
String result = "";
result += "say hello to";
result += " ";
result += "coffee candy";
System.out.println(result); 
```

### String이 불변 객체인 이유 
캐싱, 보안 동기화, 성능측면에서 이익을 얻기 위해서.  
1. 캐싱 : String을 불변하게 해 String pool에 각 리터럴 문자열의 하나만 저장해 다시 사용하거나 캐싱에 이용 가능하며, 이로 인해 힙 공간을 절약할 수 있다.  
2. 보안 : 중요한 문자열이 있는 주소의 문자열 값이 변경 가능하다면 해당 값이 변조 될 수 있다.  
3. 동기화 : 불변하기 때문에 동시에 실행되는 여러 스레드에서 안정직이게 공유가 가능하다.  

## StringBuilder
객체의 공간이 부족할 때 유연하게 늘려주어 가변적이다.   
문자열 연산(추가나 수정)할 때 주로 사용함  
클래스 내부적으로 buffer라는 독립적인 공간을 가져, 문자열을 바로 추가할 수 있어 문자열 연산 속도가 빠르다.

```
StringBuffer sb = new StringBuffer();
sb.append("say hello to");
sb.append(" ");
sb.append("coffee candy");
String result = sb.toString();
System.out.println(result); // say hello to coffee candy
```

## String vs String Buffer/String Builder
문자열의 추가, 수정, 삭제가 빈번하게 발생하는 경우에는 String Buffer/String Builder를 사용하는것이 좋다.

## String Builder vs String Buffer
StringBuilder와 String Buffer의 사용법은 동일하다.  
둘의 차이점은 StringBuffer는 멀티 스레드 환경에서 안전하고,  StringBuilder는 멀티 스레드에서 안전하지 않지만, 문자열 파싱 성능이 가장 우수하다.  