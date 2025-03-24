## PRG 패턴이란?
> PRG는 Post-Redirect-Get의 줄임말로, 웹 애플리케이션에서 중복 데이터 등록을 방지하기 위한 디자인 패턴이다.

---

### 왜 PRG 패턴을 사용하는가?

웹에서 폼을 제출할 때 일반적으로 POST 요청을 사용한다.

이 때 서버가 응답으로 단순히 HTML 페이지를 반환한다면, 사용자가 F5(새로고침)를 누를 경우 동일한 POST 요청이 다시 전송된다.

그 결과로 **데이터가 중복 저장될 수 있다**.

사용자가 같은 작업을 여러 번 수행하게 되는 문제가 발생한다.

이 문제를 해결하기 위해 PRG 패턴을 사용한다.

---

## PRG 패턴의 동작 흐름

1. **사용자가 POST 요청을 보냄**  
   예: 상품 등록 폼 제출

2. **서버는 데이터 저장 후 리다이렉트 응답 반환**  
   예: `redirect:/basic/items/{id}`

3. **클라이언트는 GET 요청을 서버에 다시 전송**  
   리다이렉트된 URL로 페이지 재요청

4. **서버는 GET 요청에 대한 응답으로 최종 결과 페이지를 보여줌**

이 과정을 통해 **폼 재전송 문제를 회피**하고,  
새로고침을 하더라도 POST 요청이 다시 발생하지 않게 된다.

---

## 코드 구현

### ❌ 잘못된 예시 (중복 저장 위험)
```java
@PostMapping("/add")
public String addItemV4(Item item){ // ModelAttribute 기능 자동으로 사용됨!
    itemRepository.save(item);
    return "basic/item";
    // 이렇게 리턴해버리면 새로고침할 때마다 새로운 아이템이 저장됨!
}
```

위와 같이 코드를 작성하게 되면 만약 post 요청 버튼을 눌러도 같은 url 주소에서 머무르기 때문에 새로고침시 같은 post 요청을 반복하게 된다.

```java
	@PostMapping("/add")
    public String addItemV5(Item item){ // ModelAttribute 기능 자동으로 사용됨!
        itemRepository.save(item);
        return "redirect:/basic/items/" + item.getId(); // +item.getId() 이런식으로 url 을 넘기면 위험함!
        // PRG(Post,Redirect,Get) 를 통해서 상품을 새로 등록하면 상품 상세페이지로 리다이렉트 되도록 함!
        // 새로고침마다 상품 등록 방지!
    }
```
따라서 redirect url 주소를 반환하도록 유도해서 post 반복을 막아야 한다.

---

#### 추가 내용 (RedirectAttributes)
위 코드에서 ` return "redirect:/basic/items/" + item.getId();` 부분이 있다.

이 부분은 url 주소가 완전히 인코딩되어 전달된 것이 아니기 때문에 다른 언어로 작성 시 문제가 될 수 있다.

>RedirectAttributes 사용
```java
	@PostMapping("/add")
    public String addItemV6(Item item, RedirectAttributes redirectAttributes){
        // RedirectAttributes 를 활용해서 더욱 안전하게 url 주소를 인코딩해서 전달함!
        Item savedItem = itemRepository.save(item);
        redirectAttributes.addAttribute("itemId", savedItem.getId());
        redirectAttributes.addAttribute("status", true);
        return "redirect:/basic/items/{itemId}";
    }
```
`RedirectAttributes` 를 사용하여 url 주소에 적절한 `parameter` 를 넣어, 완성된 url주소로 `redirect`가 가능해졌다.
