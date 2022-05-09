# 1주차
> ~ 14 useState로 상태 만들기

## react 시작하기

기존 알던 방법

```js
npx create-react-app `my-app(react 프로젝트 이름)`
```

- 리액트 동그라미가 빙글빙글 돌아가는 페이지 생성
- 필요 없는 파일, 소스를 삭제하는게 좀 오래걸림(번거로움)
- 삭제 하는 과정에서 마주치는 오류를 통해 대강 어떻게 돌아가는지 파악 가능

새로 알게된 내용

```html
<script src="https://unpkg.com/react@17/umd/react.development.js" crossorigin></script>
<script src="https://unpkg.com/react-dom@17/umd/react-dom.development.js" crossorigin></script>
<script src="https://unpkg.com/babel-standalone@6/babel.min.js"></script>

<script src="like_button.js"></script>
```
```js
// ... 복사했던 스타터 코드 ...

const domContainer = document.querySelector('#like_button_container');
ReactDOM.render(e(LikeButton), domContainer);
```

- npx creat하는 시간, node_modules 다운받는 시간 생각하면 훨씬 빠름
- 바벨, node서버 실행 등 생각하면 번거로움
- 아마 간단하게 돌릴 때, 기초 시작할 때 사용하면 좋을 듯

## 컴포넌트 - scss BEM

### [scss BEM - nana_log](https://nykim.work/15)

```html
<div class="card">
    <h2 class="card_header">
        <p class="card_header__text">To Do List</p>
        <button class="card_header__button">add</button>
    </h2>

    <ul class="card_box">
        <li class="card_box__list-header">Todo</li>
    </ul>

    <ul class="card_box-done">
        <li class="card_box-done__list-header">Done</li>
    </ul>
</div>

```
```scss
.card {
    // style
    &_header {
        // style
        &__text {
            // style
        }
        &__button {
            // style
        }
    }
    &_box {
        // style
        &__list {
            &-header {
                // style
            }
            // style
        }
        &__text {
            // style
        }
        &__ico {
            // style
        }
        &__button {
            // style
        }
    }

    &_box-done {
        // style
        &__list {
            &-header {
                // style
            }
            // style
        }
        &__text {
            // style
        }
        &__ico {
            // style
        }
        &__button {
            // style
        }
    }
}
```

장점
- scss 작성하기 편리
- 컴포넌트별로 사용하기 때문에 유사 디자인 있을 시 복붙 편함
- class명이 길기에 js에서 선택할 때에 js-~~~로 클래스 추가 (본인 이 방식 짱 좋아함.. 안헷갈림...!!)
- 개발자와 협업시, 내가 작성한 class 명이 길고 복잡하기에 과거 이상한 css 혼용될 일 없음
- id사용을 지양하기에 거의 class라 코드가 깔끔해짐

단점
- scss 작성 시 뎁스가 길어져 살짝 머리아픔
- (사내 사용 시)인수인계 할 때마다 bem알려주기 번거로움

**그래도 이왕 scss를 사용한다면 BEM이 좋은것같다**