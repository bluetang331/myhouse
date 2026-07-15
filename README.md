# 우리 동네 (myhouse)

친구랑 각자 집을 꾸미고, 서로 놀러 가는 작은 웹앱입니다.

- **내 집만** 꾸미기·저장 가능
- 친구 집은 **구경 + 방명록**만
- GitHub Pages + Firebase Realtime Database

## 배포 주소

GitHub Pages를 켜면:

`https://bluetang331.github.io/myhouse/`

## Firebase에서 꼭 할 일

코드는 이미 연결되어 있습니다. 콘솔에서 아래만 켜 주세요.

### 1. 익명 로그인

1. [Firebase Console](https://console.firebase.google.com/project/myhouse-aca77) 열기  
2. **Build → Authentication → Sign-in method**  
3. **Anonymous** → Enable → Save  

### 2. Realtime Database 규칙

1. **Build → Realtime Database → Rules**  
2. `database.rules.json` 내용을 그대로 붙여 넣고 **Publish**

이 규칙의 뜻:

- 집(`rooms`)은 누구나 읽기 가능, **자기 UID 집만** 쓰기 가능  
- 방명록은 로그인 사용자가 남길 수 있고, **작성자 또는 집 주인**만 삭제 가능  

### 3. GitHub Pages

1. GitHub 저장소 → **Settings → Pages**  
2. Source: **Deploy from a branch**  
3. Branch: `main` / folder: `/ (root)` → Save  

## 로컬에서 보기

이 앱은 Firebase CDN을 쓰므로 `index.html`을 서버로 여는 편이 좋습니다.

```bash
npx serve .
```

그다음 브라우저에서 안내된 주소로 접속하세요.
