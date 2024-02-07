



`System.out.println(store)` 메서드로 객체를 출력하던 중, 궁금한 점이 생겼다. 

어떻게 매개변수에 store 객체만 넣었을 뿐인데 `store.toString()` 와 같이 출력이 되는 것일까 ? 

<br>

## 배경

```java
			...
private static Map<Long, Member> store = new HashMap<>();

    @Override
    public void save(Member member) {
        store.put(member.getId(), member);
        System.out.println(store);
    }
			...
```

```java
{1=Member{id=1, name='memberA', grade=VIP}}
```

이 store 필드는, save메서드를 통해 member의 id값과 member 객체를  키와 값 형태로 저장하는 HashMap 타입의 저장소이다.

save메서드를 통해 store에 값을 저장한 후에 `System.out.println(store);` 를 통해 값을 살펴보니 store 객체의 주소값이 아니라 키와 값을 '='로 구분하고 '{}로 감싼 형식으로 출력된 결과를 볼 수 있었다. 어떻게 이렇게 되는 것인지 알아보자. 

<br>

1. `System.out.println(object);` 메서드가 실행되는 방식

println() 메서드는 System 클래스에 직접 정의되어 있는 것이 아니라, System 클래스에 포함되어 있는 PrintStream 타입의 static 필드인 out을 통해 사용할 수 있는 메서드이다. 

```java
/**
System의 내부 코드 중 일부이다.
이 선언은 'System' 클래스가 'PrintStream' 타입의 'out' 필드를 포함하고 있음을 보여준다.
*/
							...
public static final PrintStream out = null;
							...
```

```java
/**
PrintSteam 클래스에 있는 println(Object x) 메서드이다.
*/
public void println(Object x) {  
    String s = String.valueOf(x);  
    if (getClass() == PrintStream.class) {  
        // need to apply String.valueOf again since first invocation  
        // might return null        writeln(String.valueOf(s));  
    } else {  
        synchronized (this) {  
            print(s);  
            newLine();  
        }  
    }  
}
```

따라서, `System.out.println()`을 호출하는 것은 out 필드가 참조하는 PrintStream 객체의 println() 메서드를 호출하는 것과 같다.

<br>

2. 그래서,  System.out.println(object); 처럼, 객체를 출력하면 toString()의 형태로 출력되는 이유는 뭘까 ?

답은 PrintStream 의 public void println(object x) 메서드 안에 있는 `String.valueOf(x)`에 있다. 

 <img width="520" alt="capture 60" src="https://github.com/mksystem98/TIL/assets/147119824/c8e4a02f-c672-496b-b4d0-42c025416e23">



valueOf() 의 내부 코드를 확인해보자.

```java
public static String valueOf(Object obj) {  
    return (obj == null) ? "null" : obj.toString();  // .toString() 호출
}
```

매개변수 obj의 값이 null이라면 "null"을, 아니라면 obj의 toString()을 호출하여 반환하기 때문에, 객체를 넣으면 toString() 과 같이 출력되는 모습을 볼 수 있다.

나의 경우, store 객체를 매개변수로 넣었고, 이 store는 HashMap 의 인스턴스이므로, HashMap의 .toString()을 호출한다. 그러나 HashMap 클래스 자체에는 toString()이 정의되어 있지 않아서, HashMap이 상속받는 AbstractMap 클래스의 toString()이 사용된다. 

```java
public String toString() {  
    Iterator<Entry<K,V>> i = entrySet().iterator();  
    if (! i.hasNext())  
        return "{}";  
  
    StringBuilder sb = new StringBuilder();  
    sb.append('{');  
    for (;;) {  
        Entry<K,V> e = i.next();  
        K key = e.getKey();  
        V value = e.getValue();  
        sb.append(key   == this ? "(this Map)" : key);  
        sb.append('=');  
        sb.append(value == this ? "(this Map)" : value);  
        if (! i.hasNext())  
            return sb.append('}').toString();  
        sb.append(',').append(' ');  
    }  
}
```

AbstractMap 클래스의 toString() 내부 구조이다.

이 toString() 메서드는 맵 내의 모든 키-값을 순회하며,  {key=value, ...} 형태의 문자열을 생성하여 return하여, 위에 나왔던 결과처럼 

`{1=Member{id=1, name='memberA', grade=VIP}}`의 형태로 출력되었던 것이다. 

<br>

## 정리

1. System.out.println(object); 를 호출하면 PrintStream 클래스에 있는 println(Object x) 메서드가 호출된다.
1. PrintStream 클래스의 println(Object x) 메서드 내부에 있는 valueOf(Object obj) 메서드에서 obj.toString()을 호출한다.
1. obj의 타입에 맞는 toString()을 호출하여 return하고, 출력된다.





















