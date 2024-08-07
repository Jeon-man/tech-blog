---
title: Jest-test(1)
date: '2024-08-07'
tags: ['Test', 'Nestjs', 'Jest']
draft: false
summary: 'Nestjs에서 jest로 테스트 코드 작성하기 (1)'
---

### Nestjs에서 test 코드 작성을 위한 기본 설정 하기

---
먼저 npm 모듈을 설치한다. nestjs project는 기본적으로 설치가 되어있다.

```sh
# nestjs 프로젝트를 만들 때 기본적으로 설치 됨
yarn add -D @nestjs/testing jest @types/jest ts-jest
```

현재 프로젝트에서는 nestjs 10.* 버전을 사용하고 있다.

```
root/
├── src/
│   ├── @types
│   ├── utils/
│   └── modules/
│       ├── app/
│       ├── config/
│       ├── langchain/
│           └── langchain.service.ts
│           └── langchain.controller.ts
│           └── langchain.types.ts
├── test/
│   ├── test files
├── package.json
└── tsconfig.json
```

설정 후 `yarn test`를 했는데 에러가 발생했다.
```
Cannot find module '@module/vectorStore/file/file.vectorStore.strategy' from 'modules/langchain/langchain.service.ts'
```

에러를 확인해보니 type path를 찾지 못하고 있어, jest에서는 config 파일에 type path를 따로 지정을 해줘야했다.


현재 모듈 구조는 `src/module/langchain -> @module/langchain` 식으로 type path를 적용하고 있다.

```json
// tsconfig.paths.json
{
  "compilerOptions": {
    "baseUrl": "./",
    "paths": {
      "@module/*": ["./src/modules/*", "./src/modules/*/index"],
      "@lib/*": ["./src/lib/*"],
      "@util/*": ["./src/utils/*"]
    }
  }
}

```

아래와 같이 type path를 지정하면 테스트 중 import 파일에 있는 type path들을 불러올 수 있다.

```json
// package.json
...
"jest": {
    ...
    "rootDir": "src",
    "moduleNameMapper": {
      "^@module/(.*)$": "<rootDir>/modules/$1",
      "^@lib/(.*)$": "<rootDir>/lib/$1",
      "^@util/(.*)$": "<rootDir>/utils/$1"
    }
}
```
---
#### e2e test

nestjs 프로젝트에서 jest-e2e.json은 root에 test에 있다.
```
root/
├── src/
│   ├── @types
│   ├── utils/
│   └── modules/
├── test/
│   ├── jest-e2e.json
├── package.json
└── tsconfig.json
```

e2e 테스트에 대한 config 파일이 존재하지만 e2e에서도 type path를 못 불러오기에 추가적인 설정을 해야한다.

```json
// jest-e2e.json
{
  "moduleFileExtensions": ["js", "json", "ts"],
  "rootDir": ".",
  "testEnvironment": "node",
  "testRegex": ".e2e-spec.ts$",
  "transform": {
    "^.+\\.(t|j)s$": "ts-jest"
  },
  // 아래와 같이 추가
  "preset": "ts-jest",
  "moduleNameMapper": {
    "^@module/(.*)$": "<rootDir>/../src/modules/$1",
    "^@lib/(.*)$": "<rootDir>/../src/lib/$1",
    "^@util/(.*)$": "<rootDir>/../src/utils/$1"
  }
}
```

e2e json은 root dir이 rootPath/test로 잡혀있어 `<rootDir>/../src`를 앞에다 추가해 위치를 지정해줬다.

---

### 최종 테스트 결과

```sh
yarn test
# 결과
 PASS  src/modules/app/app.controller.spec.ts
  AppController
    root
      ✓ should return "Hello World!" (14 ms)

Test Suites: 1 passed, 1 total
Tests:       1 passed, 1 total
Snapshots:   0 total
Time:        4.412 s, estimated 5 s
Ran all test suites.
✨  Done in 5.14s.
```

```sh
yarn test:e2e
# 결과
 PASS  test/app.e2e-spec.ts (5.37 s)
  AppController (e2e)
    ✓ / (GET) (144 ms)

Test Suites: 1 passed, 1 total
Tests:       1 passed, 1 total
Snapshots:   0 total
Time:        5.439 s, estimated 7 s
Ran all test suites.
Jest did not exit one second after the test run has completed.

'This usually means that there are asynchronous operations that weren't stopped in your tests. Consider running Jest with `--detectOpenHandles` to troubleshoot this issue.
✨  Done in 16.50s.
```

성공적으로 테스트 설정을 완료 후 테스트까지 완료됐다.
