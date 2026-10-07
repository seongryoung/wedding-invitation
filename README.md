# 모바일 청첩장

GitHub Pages에 바로 배포할 수 있는 정적 모바일 청첩장입니다. 방명록/RSVP는 Firebase Firestore를 사용합니다.

## 1. 내 정보로 변경
`index.html`에서 이름, 예식일, 장소, 전화번호, 계좌번호를 검색해 교체하세요. `app.js` 상단 `WEDDING_DATE`도 변경하세요.

사진은 아래 이름으로 넣습니다.
- `assets/images/main.jpg`
- `assets/images/gallery-01.jpg` ~ `gallery-09.jpg`

## 2. Firebase 방명록 연결
1. Firebase Console에서 프로젝트 생성
2. 프로젝트 설정 > 내 앱 > Web 앱 추가
3. 표시되는 `firebaseConfig`를 `firebase-config.js`에 복사
4. Firestore Database 생성
5. Firestore > Rules에서 `firestore.rules` 내용을 붙여넣고 Publish

주의: 현재 예제는 간편한 공개 청첩장을 위한 최소 규칙입니다. 스팸 방지를 위해 운영 시 App Check/Cloud Functions 또는 별도 인증을 추가하는 것을 권장합니다. 방명록 비밀번호는 예제 UI에 있지만 클라이언트만으로 안전한 삭제 인증을 구현할 수 없으므로 현재 삭제 기능은 비활성화되어 있습니다.

## 3. GitHub Pages 배포
1. GitHub에서 새 repository 생성 (예: `wedding-invitation`)
2. 이 폴더의 파일 전체를 repository 루트에 push
3. Repository > Settings > Pages
4. Build and deployment의 Source를 `Deploy from a branch`로 선택
5. Branch `main`, Folder `/(root)` 선택 후 Save
6. 잠시 후 `https://GITHUB_ID.github.io/wedding-invitation/` 로 접속

### 터미널로 올리기
```bash
git init
git add .
git commit -m "Initial wedding invitation"
git branch -M main
git remote add origin https://github.com/YOUR_ID/wedding-invitation.git
git push -u origin main
```

## 4. 커스텀 도메인 (선택)
Settings > Pages > Custom domain에서 보유 도메인을 연결할 수 있습니다.
