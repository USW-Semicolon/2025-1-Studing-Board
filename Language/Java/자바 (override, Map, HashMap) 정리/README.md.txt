# @Override와 Map, HashMap 설명 정리

## `@Override`
- 인터페이스에 있는 메서드를 재정의한다는 표시

 

### ex) MemberReposiotry (interface)

```java
public interface MemberRepository {

    void save(Member member);

    Member findById(Long memberId);
}
```

MemberRepository 인터페이스가 있다 하면,

MemoryMemberRepository를 만들어 save() 와 findById() 메서드를 반드시 정의해줘야 한다.

↓

### ex) MemoryMemberRepository

```java
import java.util.HashMap;
import java.util.Map;

public class MemoryMemberRepository implements MemberRepository{

    private static Map<Long, Member> store = new HashMap<>();
    @Override
    public void save(Member member) {
        store.put(member.getId(), member);
    }

    @Override
    public Member findById(Long memberId) {
        return store.get(memberId);
    }
}
```
여기서 Map<long, Member>는?

new HashMap<>()은?

 

`Map`
"키 - 값 쌍(key-value pair) 로 데이터를 저장하는 자료구조"

Long -> key(열쇠)

Member -> Value(값)

= 회원 ID(Long)를 키로 하고,

해당 회원 객체(Member)를 값으로 저장하는 저장소

 

`new HashMap<>()`
- HashMap은 Map의 대표적인 구현 클래스

- new HashMap<>() 은 빈 맵 객체를 생성.

** 아무 데이터도 없는 Map을 새로 만든다는 뜻 **

 

Map은 '인터페이스'라서 직접 못 씀.

HashMap 같은 '구현체'로 만들어야 실제로 동작.

 

즉,
```java
private static Map<Long, Member> store = new HashMap<>();
```
***

클래스 전체에서 공유할 수 있는 (static),

Long 타입의 ID와 Member 객체를 저장하는 Map을 하나 만들고,

그것을 HashMap 구현체로 초기화한다.

***

 
```java
public void save(Member member) {
    store.put(member.getId(), member);
}
```
***

전달받은 회원 객체를 ID기준으로 저장

***

 
```java
@Override
public Member findById(Long memberId) {
    return store.get(memberId);
}
```
***

ID로 회원을 찾아서 반환

***