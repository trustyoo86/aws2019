# Building Modern APIs With GraphQL

## REST vs GraphQL

### REST

- list마다 LOOP돌며 처리

### grpahql

- 1개의 커넥션
- non nullable thing
- non nullable list

```
query {
    person(name: "parmas") {
        name
        films {

        }
    }
}
```

- request (Graphql doc) => response JSON
- 언어 특정
- 스키마 (domain-specific)
- Server implementation

### GraphQL은

- graph database가 아니다
- client-side solution이 아니다
- Facebook graph API가 아니다
- 특정 데이터베이스에 제한이 없다
- Nodejs / Javascript에 제한적이지 않다 (Java등에도 적용 가능)
- HTTP에 제한적이지 않다

### 동작

Query - Read
Mutation - Write
Subscription - Observe Event

Single response가 아님

### code

```
query GetBooksForAuthor($id: ID!) {
    author(id: $id) {
        givenName
    }
}
```

* query: 로 시작함
* GetBooksForAuthor: Debugging 용이
* $id: parameter

### Building the server

- entry points? 
- resolvers => resolver들 모임으로 작성

### resolvers 구성

```typescript
export class SpeciseResolver {
    @query(retuerns => [Species])
    public greet() {
        return "";
    }
}

export async function buildAppSchema() {
    retrn await buildSchema({
        resolvers: [
            SpeciseResolver,
        ]
    })
}
```

### History
- 2012: Facebook mobile app
- 2015: Open source
    - language
    - js
    - 두개로 이원화
- 2018: GraphQL Foundation

### GraphQL이 있다고 REST가 죽나?

#### Rest vs GraphQL

- Definition 공유(Documents) : N / Y
Grpahql은 Document 그대로다 :)

- Concept : Resources / Graphs
Rest는 서버의 리소스 정의 / GraphQL은 Graph 데이터를 기반으로 구현

- 조직 (리소스 관리): Federated(연합) / Centralized(중앙 집중)

- 관계지향 : Y / N
Rest는 자원을 정의하고, 각 api들을 관리하고 있기 때문에 관계 지향적임 / GraphQL은 document그대로임

- 내부지원: N /Y
Rest는 Swagger등을 써야하나 GraphQL은 Playground 존재

- 데이터 타입: Weak / Strong

- 실시간 지원: N / Y

### Modern API
- Efficiency
- Predictability
- Versioning
- Security
- Documentation
- Tooling
- Caching
- Database integration

1) Efficiency

* overfetching: Rest는 data가 너무 많음..
* Underfetching: 데이터가 충분하지 않아 다른 REST api 호출됨..
* client-side이 에러핸들링, 로직 처리를 줄임
- single network request로 data 조작 가능

2) Type Safety
* predictability
* Native clients
* Code gen

3) Domain modeling
* Domain-driven design
* shared language

- schema, graph
- versioning이 필요없음 :)

### 언제사용하나?

- 기능이 많아지는 경우 


### Getting GraphQL

* donot

- 전체 스키마를 다 설계하지 말아라
- REST API 하나에 대한 기능을 바꾸지 말아라
- 비즈니스 로직을 GraphQL Layer에 올리지 말아라


