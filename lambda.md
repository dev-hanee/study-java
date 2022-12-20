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
- 
