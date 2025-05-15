# Zustand 학습

## Zustand란?

> 작고 빠르며 확장 가능한 React 상태관리 라이브러리이다.

## Store란?

- 스토어는 애플리케이션의 여러 상태를 중앙에서 관리하는 패턴
  - 상태는 관리하는 데이터를 뜻함
- 컴포넌트 간 데이터를 쉽게 공유하고 데이터 변경을 감지해 자동으로 렌더링할 수도 있다.

### 애플리케이션의 컴포넌트 구조 및 데이터 전달

![component](https://somwpkzlplaovldnfahk.supabase.co/storage/v1/object/public/heropy.dev_posts/n74Tgc/s1.png)

- 기본적으로 React는 상위컴포넌트에서 하위컴포넌트로 단방향 흐름이다. -> `props 방식`

![props](https://somwpkzlplaovldnfahk.supabase.co/storage/v1/object/public/heropy.dev_posts/n74Tgc/s2.png)

- props 방식은 중첩된 컴포넌트 구조에서 불필요하게 데이터를 취급하는 중간 단계의 컴포넌트가 생겨 컴포넌트 간의 결합도가 높아지며 유지/보수가 어려워진다.

![props_problem](https://somwpkzlplaovldnfahk.supabase.co/storage/v1/object/public/heropy.dev_posts/n74Tgc/s3.png)
![props_problem_2](https://somwpkzlplaovldnfahk.supabase.co/storage/v1/object/public/heropy.dev_posts/n74Tgc/s4.png)

> 이것을 `Prop Drilling`이라고 한다.

```
Prop Drilling을 해결하기 위해서 Store를 사용하여

컴포넌트 간 공유할 데이터를 중앙에서 관리할 수 있도록 한다.
```

- 이러한 방식은 데이터를 전달하는 중간 단계 컴포넌트가 필요하지 않으므로 컴포넌트 간 결합도를 낮추고 유지/보수를 쉽게 한다.

![prop_drilling_solution](https://somwpkzlplaovldnfahk.supabase.co/storage/v1/object/public/heropy.dev_posts/n74Tgc/s5.png)
![prop_drilling_solution](https://somwpkzlplaovldnfahk.supabase.co/storage/v1/object/public/heropy.dev_posts/n74Tgc/s6.png)

## Zustand의 패턴

> Zustand의 패턴은 간소화된 Flux 패턴을 사용한다.
>
> ![Flux Pattern](https://velog.velcdn.com/images/jyooj08/post/fcb2a8c5-2d8f-4535-bf25-af39246c42d6/image.png)

## 참고자료

- [공식문서](https://zustand.docs.pmnd.rs/getting-started/introduction)
- [HEROPY.DEV](https://www.heropy.dev/p/n74Tgc)
- [jyooj08 - velog](https://velog.io/@jyooj08/Zustand-%ED%95%9C-%EB%B0%A9%EC%97%90-%EC%A0%95%EB%A6%AC)
- [chairking-95 - tistory](https://chairking-95.tistory.com/175)
