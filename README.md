📚 목차
2026-04-29 React 웹 개발 & 스타일링
2026-04-08 조건부 렌더링 & 리스트 렌더링
2026-04-01 JSX & Props
2026-03-25 React 컴포넌트 & Vite
2026-03-18 React 프로젝트
2026-03-11 Git & Node.js 기초
📅 2026-04-29 — React 웹 개발 & 스타일링
✅ 컴포넌트 기반 개발

웹 개발은 컴포넌트 단위로 구성됩니다.

id → 특정 요소에만 사용
class → 여러 요소에 재사용 가능 (권장)
핵심
id는 재사용이 어려움
class 기반 설계가 유지보수에 유리
🎨 스타일링 방식
1. 일반 CSS
.button {
  background: blue;
  color: white;
}
import './styles.css';

<button className="button">Click</button>
장점
간단함
단점
클래스 충돌 가능
2. 인라인 스타일
<button style={{ backgroundColor: 'blue' }}>
특징
빠르게 작성 가능
유지보수 어려움
3. CSS Module
import styles from './Button.module.css';

<button className={styles.button}>
특징
클래스 충돌 방지
컴포넌트별 스타일 관리 가능
4. CSS Framework
<button className="bg-blue-500 text-white px-4 py-2">
대표 예시
Tailwind CSS
Bootstrap
Bulma
🖱 이벤트 핸들러
function handleClick() {
  alert("클릭됨!");
}

<button onClick={handleClick}>Click</button>
⚠ 이벤트 처리 주의
onClick={handleClick}   // ⭕
onClick={handleClick()} // ❌
✅ 핵심 정리
컴포넌트 기반 개발
CSS Module 활용 권장
이벤트는 함수 형태로 전달
유지보수 고려 중요
📅 2026-04-08 — 조건부 렌더링 & 리스트 렌더링
✅ 조건부 렌더링

조건에 따라 다른 UI를 출력하는 방식입니다.

사용 방법
if문
삼항 연산자
&& 연산자
예시
function App({ isLogin }) {
  return (
    <>
      {isLogin ? <h1>환영합니다</h1> : <h1>로그인 해주세요</h1>}
    </>
  );
}
✅ 리스트 렌더링

배열 데이터를 기반으로 UI를 반복 생성합니다.

핵심 개념
map() → 반복 생성
filter() → 조건 처리
key → 요소 구분
예시
const heroes = [
  '스파이더맨',
  '아이언맨',
  '배트맨'
];

export default function MovieHeroes() {
  const listHeroes = heroes.map(hero => <li>{hero}</li>);

  return <ul>{listHeroes}</ul>;
}
📅 2026-04-01 — JSX & Props
✅ JSX란?

JavaScript 안에서 HTML 형태 UI를 작성할 수 있는 문법입니다.

<h1>Hello React</h1>
✅ JSX 규칙
부모 요소 하나로 감싸기
모든 태그 닫기
camelCase 사용
✅ JSX에서 JavaScript 사용
export default function UseJsx() {
  const name = "React";

  return (
    <>
      <h1>Hello, {name}!</h1>
    </>
  );
}
✅ Props

컴포넌트 간 데이터를 전달하는 방법입니다.

부모 컴포넌트
<Items name="여벌 옷" isPacked={true} />
자식 컴포넌트
function Items({ name, isPacked }) {
  return <li>{name}</li>;
}
✅ Spread Props
const props = { name: "Kim", age: 20 };

<User {...props} />
📅 2026-03-25 — React 컴포넌트 & Vite
✅ React 컴포넌트 기본 구조
export default function Profile() {
  return (
    <>
    </>
  );
}
✅ 컴포넌트 분리
Profile.jsx
export default function Profile() {
  return <img src="..." />;
}
App.jsx
import Profile from "./Profile";

export default function App() {
  return <Profile />;
}
✅ 컴포넌트 중첩
function Gallery() {
  return (
    <>
      <Profile />
      <Profile />
    </>
  );
}
✅ Export 방식
Default Export
export default function A() {}
import A from "./A";
Named Export
export function A() {}
import { A } from "./A";
✅ Vite & SWC
SWC
Rust 기반 컴파일러
빠른 TypeScript 변환 지원
Oxc
ESLint + TypeScript 통합 목표
SWC보다 더 빠른 성능 목표
📅 2026-03-18 — React 프로젝트
✅ React 프로젝트 생성
설치 방법
React 프레임워크 없이 개발
기존 프로젝트에 React 연결
새로운 React 앱 생성
✅ 컴포넌트 개념
컴포넌트 역할 이해
이름 규칙
첫 컴포넌트 만들기
📅 2026-03-11 — Git & Node.js 기초
✅ Git 학습 방법
초급
git init
git add .
git commit -m "설명"
git remote add origin URL
고급
git cherry-pick
git reset --soft HEAD~1
git revert
git reflog
✅ .gitignore

Git 버전 관리에서 제외할 파일 목록 설정

node_modules
.env
dist
✅ Node.js
2009년 Ryan Dahl 발표
비동기 논블로킹 처리
JavaScript 풀스택 개발 가능
npm 패키지 사용 가능
✅ React 이전 vs 이후
이전 방식
HTML/CSS 구성
JavaScript로 DOM 직접 수정
React 이후
상태(state) 기반 렌더링
DOM 직접 수정 감소
유지보수 향상
🚀 최종 핵심 정리
React는 컴포넌트 기반 구조
JSX를 사용하여 UI 작성
props로 데이터 전달 가능
조건부 렌더링 가능
배열 기반 UI 생성 가능
Git을 통해 버전 관리 수행
CSS Module과 Tailwind 활용 증가 중
