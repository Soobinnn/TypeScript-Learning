# TypeSciprt 개발환경 설정

TypeScript로 개발 하기 위해서는 nodeJS가 설치되어 있어야 한다.

```
# typescript 컴파일러 설치
npm install -g typescript

#package.json 생성
npm init

# tsconfig.json 생성
tsc --init
```

TypeScript 컴파일러는 TypeScript파일 (.ts)를 자바스크립트 파일로 트랜스파일링한다.

> 컴파일은 일반적으로 소스 코드를 바이트 코드로 변환하는 작업을 의미한다. <br/> TypeScript 컴파일러는 TypeScript파일을 자바스크립트 파일로 변환하므로 컴파일보다는 트랜스파일링이 보다 적합하다.

### tsconfig.json

#### compileOptions

- taget

  javascript로 변환할 때의 ECMA버전

- module

  Javascript에서 범용적인 사용을 위해 모듈화를 할 때 사용되는 방식을 명시 <br/> (대표적인 예 : AMD/CommonJS)

- sourceMap

  디버그가 가능하도록 해주는 SourcveMap 생성여부

- outDir

  컴파일된 파일의 위치를 지정함. (deafault ts파일과 동일한 디렉토리에 생성됨)

- include

  ts파일의 범위를 지정함. <br/> ex) nodue_modules같은 디렉토리는 컴파일 할 필요가 없고 컴파일 시 매우 느리다.

## 예제

src 폴더 생성 후 - example.ts 파일을 만든다.

```typescript
```

## VS Code 환경설정

### nodejs Path 설정

내 PC 고급설정 - 환경변수 Path에 nodejs 경로를 추가한다.

### tsc와 연동

build를 매번 tsc 치면서 할 수 없으니 vscode task와 연결한다.

vscode에서 **ctrl+shift+B** 를 누르면 build task가 실행된다.<br/> (**ctrl+shift+P** 를 누른 후 Tasks:Configure Default build task를 누를 것과 동일)

.vscode 디렉토리 안에 tasks.json이라는 파일이 생성된다.

생성된 tasks.json 파일에 "label"을 추가한다.<br/>추후에 build 선택할 떄 구분하기 쉽게하기 위함.

```
{
  // tasks.json 형식에 대한 설명서는
  // https://go.microsoft.com/fwlink/?LinkId=733558의 내용을 참조하세요.
  "version": "2.0.0",
  "tasks": [
    {
      "type": "typescript",
      "tsconfig": "ex_typescript_start/tsconfig.json",
      "problemMatcher": ["$tsc"],
      "group": {
        "kind": "build",
        "isDefault": true
      },
      "label": "Run tsc build"
    }
  ]
}

```

# 참고 자료

https://typescript-kr.github.io/pages/tutorials/TypeScript%20in%205%20minutes.html

https://velog.io/@jihoson94/TypeScript-%EC%8B%9C%EC%9E%91%ED%95%98%EA%B8%B0-2kk4mmeqow

https://ipex.tistory.com/entry/TypeScript-TS-%ED%99%98%EA%B2%BD-%EC%84%A4%EC%A0%95-with-webpack-v4TypeScript-Environment-Configuration-with-webpack-v4?category=811949
