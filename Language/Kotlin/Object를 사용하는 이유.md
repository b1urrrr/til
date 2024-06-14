## Object를 사용하는 이유
### 컴파일 코드
```
public final class Singleton {
   public static final Singleton INSTANCE;

   static {
      Singleton var0 = new Singleton();
      INSTANCE = var0;
   }
}
```
- 내부적으로 INSTANCE 객체가 생성되어 간편하게 싱글톤 구현 가능
- Kotlin 파일에서 인스턴스를 참조하지 않고도 싱글톤 리소스에 접근 가능 (가독성 개선)
- Java 파일에서는 `Singleton.INSTANCE`을 통해 인스턴스 접근 가능
