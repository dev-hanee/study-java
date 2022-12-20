## functional interface
- method 가 하나인 interface
- functional interface 는 method 가 하나 이므로 interface 의 존재 이유 및 목표가 명확하다. 

```
public interface Printable {
   void print(String);
}

class Machine implement Printable {
   public void print(String content) {
       System.out.println(content + " from Machine")
   }
}

class Main {
   public static void main() {
     Machine m = new Machine();
     m.print();
   }
}
```

Or

```
public interface Printable {
   void print(String);
}

class Machine implement Printable {
   public void print(String content) {
       System.out.println(content + " from Machine")
   }
}

class Main {
   public static void main() {
     Machine m = new Machine();
     Print(m);
   }
   
   public Print(Printable p) {
      p.print();
   }
}
```

## lambda 의 도입
- functional interface 는 사용할 때 불필요한 코드를 작성하게 됨. 
- 필요한 것은 functional interface 에 포함되어 있는 method 하나 이지만, 이를 구현하기 위해서는 class 부터 instance 생성 코드까지 모두 작성해야 함. 
- 이는 functional interface 의 목적 및 사용 방법이 명확한데 비해 불필요한 코드를 작성해야 함. 
- 그래서 클래스 및 함수 이름 등을 제외하고 함수 본체만 사용해서 functional interface 를 사용할 수 있게 함. 이것이 lambda 함수

/*Lambda 함수에서는 정의만 하고, labmda 함수를 받는 곳에서 이를 사용함. (매개변수 입력 포함)*/
```
public interface Printable {
   void print(String);
}

class Main {
   public static void main() {
       Print((content) -> System.out.println(content + "from Machine"))
   }
   
   public Print(Printable p) {
      p.print("This is content");
   }
}
```
