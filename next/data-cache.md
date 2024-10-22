# 데이터 캐시

데이터 캐시(Data Cache)란 fetch 메서드를 활용해 불러온 데이터를 Next 서버에서 보관하는 기능이다. 그래서 영구적으로 데이터를 보관하거나 특정 시간을 주기로 갱신 시키는 것도 가능하다. 이는 불필요한 데이터의 요청수를 줄여서 웹서비스의 성능을 크게 개선할 수 있게 된다.

> 데이터 캐시 옵션은 오직 fetch 메서드에서만 활용 가능하다.

#### no-store

```javascript
const response = await fetch(`~/api`, { cache: "no-store" });
```

- 데이터 페칭의 결과를 저장하지 않는 옵션
- 캐싱을 아예 하지 않도록 설정

#### force-cache

```javascript
const response = await fetch(`~/api`, { cache: "force-cache" });
```

- `no-store`와 반대로 요청의 결과를 무조건 캐시하는 옵션
- 한번 호출된 이후에는 다시는 호출되지 않는다.

#### revalidate

```javascript
const response = await fetch(`~/api`, { next: { revalidate: 3 } });
```

- 특정 시간을 주기로 캐시를 업데이트하는 옵션
- 마치 Page Router의 ISR 방식과 유사

#### tags

```javascript
const response = await fetch(`~/api`, { next: { tags: ["a"] } });
```

- On-Demand Revalidate 옵션
- 요청이 들어왔을 때 데이터를 최신화한다.
