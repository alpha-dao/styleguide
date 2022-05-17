# styleguide

## Git

### Commit message Conventions

<https://gist.github.com/stephenparish/9941e89d80e2bc58a153>

### Branch Conventions

`<type>(<scope>)/<jira-ticket-number>`

#### type

- feat (feature)
- fix (bug fix)
- docs (documentation)
- style (formatting, missing semi colons, …)
- refactor
- test (when adding missing tests)
- chore (maintain)

## Typescript

### Project structure and File naming conventions

export 기준으로 나눕니다.

1. Type alias 또는 Interface, Abstract Class, Class를 export 할 경우 `PascalCase`로 작성합니다.
2. Function export 할 경우 `kebab-case`로 작성합니다.

### Variable naming conventions

Use `camelCasae`

### Don't use if else chain

- before

```javascript
if (condition) {
    // do something
} else {
    // do something
}
```

- **after**

```javascript
if (condition) {
    // do something
}

// do something
```

- 특수케이스) Mutable 변수를 바꾸는 상황

```javascript
let a = 1;
if (condition) {
    a = 0
} else {
    a = 1
}
```

### inline variable

- 함수의 리턴타입을 적고, Promise 단일을 리턴해야할 경우 `return Promise` 를 한다.

```javascript
const exec = async () => {
    const promiseGenerate = async () => {
        console.log("promiseGenerate");
    }

    // O return promise + exec function return type
    return promiseGenerate()

    // X 변수 + await in funciton
    const result = await promiseGenerate()
    return result
 
    // X return await promise 
    return await promiseGenerate()
}
```

### Function

#### Argument Type

```javascript
// - before
type Arg = card_release & { card_candidate: card_candidate[] }
const getMinimumCandidateNumber = (arg: Arg) => {
    return arg.card_candidate.map(candidate => candidate.number).max()
}

// - after
const getMinimumCandidateNumber = (arg: card_candidate[]) => {
    return arg.map(candidate => candidate.number).max()
}

```

## Discussion

### ing

- line width 설정 (120자)

## Reference

<https://google.github.io/styleguide/tsguide.html#syntax>
