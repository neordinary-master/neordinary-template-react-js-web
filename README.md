# Welcome to neordinary-template-web-react-js
![Version](https://img.shields.io/badge/version-1.0.0-blue.svg?cacheSeconds=2592000)
#### [License: Only use for softsquared project]

### 🏠 [템플릿 페이지](http://localhost:3000)
### 🗺 [GitLab 소스](https://gitlab.com/softsquared/tech-department/outsource/template-outsource/neordinary-template-web-react-js)
#

## Prerequisites
*
- npm = 8.5.0
- node = v16.14.2

#

## 설치법
*
```sh
npm install

or

npm install --force
```

#

## 로컬 실행법 / 배포 소스 빌드법
*
```sh
npm run start

npm run build-dev // Local 환경에서 개발을 완료하고 바로 서버로 Push 했을 경우 작동이 안되는 경우 (node version, os version, security group 보안설정)

npm run build-stage //

npm run build-prod //
```

#

## 저작권자
*
👤 **(주)소프트스퀘어드**

#

## 구조

> 폴더구조
```
.
├── manifests/
| └── AndroidManifest.xml
|
└──java
├── config/
| ├── ApplicationClass
| ├── BaseActivity
| ├── BaseFragment
| ├── BaseResponse
| └── XAccessTokenInterceptor
├── src/
| └── 큰 도메인/
| ├── 작은 도메인/
| | ├── models/
| | ├── Fragment
| | ├── FragmentInterface
| | ├── Retrofitinterface
| | └── Service
| └── Activity
└── util/
```

----

> config 폴더
```

근간이 되는 코드들이 위치해 있습니다.

< ApplicationClass >

앱이 실행될 때 맨 처음 실행되는 코드들이 위치해 있습니다.
따라서 각종 전역변수와 앱이 실행될 동안 한 번만 유지되면 되는 객체(싱글톤 객체)들을 생성하는 코드들이 위치해 있습니다.


< BaseActivity & BaseFragment >

예를들어 로딩창을 띄우는 것, 토스트 메세지 띄우는 것등 자주 쓰이지만, 중복이 많이 되는 코드들 모듈화 하여 작성한 코드들이 위치해 있습니다.
따라서 여러 화면에서 공통적으로 사용되는 기능을 이곳에 모듈화 하여 작성한 후 필요한 곳에서 가져다 사용하시길 추천드립니다.


< XAccessTokenInterceptor >

이 부분은 코드를 따로 건드릴 필요는 없는 부분입니다.
네트워크 통신을 할때, jwt토큰 헤더설정 등과 같이 네트워크 통신 관련하여 공통적으로 처리해야 하는 것들을 설정하는 코드가 위치해 있습니다.


```

----

> src 폴더
```

src 폴더는 Config/ 의 베이스 코드들을 기반으로, Activity나 Fragment 등을 동작시키는
즉 앱을 동작시키는 구체적인 구현을 코드들이 위치해 있습니다.

src 폴더는 도메인(화면)별로 폴더가 나눠져있다고 생각하시면 됩니다.
src 폴더의 구조는 메인화면, 스플래쉬 화면 등 큰 도메인별로 나눠져있고, Fragment별 작은 도메인으로 나눠져있습니다.
예를들어 메인화면이라는 큰 도메인 폴더안에, 홈 화면과 내정보 화면등 과 같은 작은 도메인 폴더들이 있습니다.

- models : 오고가는 데이터의 형식들이 위치해 있습니다.
- Servie : 네트워크를 담당하는 코드들이 위치해 있습니다.
- Activity & Fragment : 뷰를 만들고, 네트워크 요청을 보내주는 코드들이 위치해 있습니다.
- RetrofitInterface : 네트워크
