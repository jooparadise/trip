# WayTrip — AI 여행 플래너

Google Login + Drive 연동 여행 계획 앱입니다.

---

## 🚀 빠른 시작 (GitHub Pages)

### 1. Google Cloud Console 설정

1. [Google Cloud Console](https://console.cloud.google.com) 접속
2. 새 프로젝트 생성 (예: `waytrip-app`)
3. **APIs & Services → Library** 에서 두 가지 활성화:
   - `Google Drive API`
   - `Google Identity Services`
4. **APIs & Services → Credentials → Create Credentials → OAuth 2.0 Client ID**
   - Application type: **Web application**
   - Name: `WayTrip`
   - Authorized JavaScript origins:
     ```
     https://YOUR_GITHUB_USERNAME.github.io
     http://localhost:3000
     ```
   - Authorized redirect URIs: (비워도 됨 — 팝업 방식 사용)
5. 생성된 **Client ID** 복사 (형태: `xxxx.apps.googleusercontent.com`)

### 2. index.html에 Client ID 입력

`index.html` 파일 상단의 CONFIG 섹션을 수정하세요:

```javascript
// 변경 전
const GOOGLE_CLIENT_ID = 'YOUR_GOOGLE_CLIENT_ID.apps.googleusercontent.com';

// 변경 후 (실제 값으로)
const GOOGLE_CLIENT_ID = '123456789-abc.apps.googleusercontent.com';
```

### 3. GitHub Pages 배포

```bash
# 저장소에 push
git add index.html
git commit -m "Add WayTrip app"
git push

# GitHub 저장소 Settings → Pages → Source: main branch, / (root)
# 약 1-2분 후 https://YOUR_USERNAME.github.io/REPO_NAME 에서 접속 가능
```

---

## 🔑 API 키 없이 체험하기

Client ID를 설정하지 않아도 **"비로그인으로 체험하기"** 버튼으로 모든 기능을 테스트할 수 있습니다.  
단, Google Drive 저장/불러오기 기능은 로그인 후에만 작동합니다.

---

## 📋 기능 목록

| 기능 | 설명 |
|------|------|
| Google OAuth | 팝업 방식 소셜 로그인 |
| Drive 자동저장 | 3초 딜레이 후 자동 저장 |
| Drive 불러오기 | 로그인 시 이전 계획 자동 복원 |
| 경유지·방문지 | 자유 추가/삭제 |
| AI 루트 생성 | 카테고리·교통수단 기반 루트 |
| 구글맵 연동 | 전체 경로 / 일별 구간 / Save List |
| 날씨 표시 | OpenWeatherMap API 연동 가능 |
| 로컬 이벤트 | 무료/유료 필터, 루트 추가 |
| 경비 정리 | 추가/삭제/CSV 내보내기 |
| 주유소 추천 | 경로 상 주유소 및 가격 |

---

## 🌤 날씨 실시간 연동 (선택)

`index.html`에서 날씨 섹션을 실제 데이터로 교체하려면:

1. [OpenWeatherMap](https://openweathermap.org/api) 무료 API 키 발급
2. `index.html` 내 `fetchWeather()` 함수 주석을 해제하고 키 입력

---

## 📁 파일 구조

```
/
└── index.html   ← 단일 파일 앱 (모든 기능 포함)
└── README.md
```

---

## 📄 라이선스

MIT License
