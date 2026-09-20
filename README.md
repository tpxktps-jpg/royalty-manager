# 작품 관리 웹앱

기존 단일 HTML 프로그램을 Firebase Hosting에 배포할 수 있도록 정리한 버전입니다.

## Firebase 최초 배포

1. Firebase Console에서 프로젝트와 Hosting을 만듭니다.
2. Authentication에서 이메일/비밀번호 로그인을 활성화하고 Firestore Database를 만듭니다.
3. Firebase 프로젝트 `royalty-manager-ef557`이 `.firebaserc`와 웹 앱에 연결되어 있습니다.
4. 터미널에서 `firebase login` 후 `firebase deploy --only hosting,firestore:rules`를 실행합니다.
5. 사이트의 `클라우드 연결`에서 이메일 계정을 만들고 같은 계정으로 각 기기에 로그인합니다.

## GitHub 자동 배포 연결

Firebase CLI 로그인 후 프로젝트 폴더에서 아래 명령을 한 번 실행합니다.

```bash
firebase init hosting:github
```

연결할 GitHub 저장소를 선택하면 Firebase가 필요한 GitHub Actions 워크플로와 배포 권한을 안전하게 구성합니다.

## 데이터 관련 주의

입력 데이터는 브라우저에 즉시 저장되며 로그인 상태에서는 Firestore에도 자동 저장됩니다. 다른 기기에서 동일한 이메일 계정으로 로그인하면 클라우드 데이터를 불러옵니다. 각 사용자의 데이터는 Firebase 보안 규칙으로 본인 계정에서만 읽고 쓸 수 있습니다.
