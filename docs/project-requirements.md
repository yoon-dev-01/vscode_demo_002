# Next.js + Supabase 웹 애플리케이션 PRD

## 1. 프로젝트 초기 설정

### 1.1 프로젝트 생성

```bash
npx create-next-app@latest -e with-supabase my-app
cd my-app
```

### 1.2 초기 설정 옵션

- TypeScript: ✅
- Tailwind CSS: ✅
- `src/` directory: ❌
- App Router: ✅
- Import alias: ✅

## 2. 프로젝트 구조

```
my-app/
├── app/
│   ├── (auth)/
│   │   ├── sign-in/
│   │   │   └── page.tsx
│   │   ├── sign-up/
│   │   │   └── page.tsx
│   │   └── callback/
│   │       └── route.ts
│   ├── protected/
│   │   └── page.tsx
│   └── page.tsx
├── components/
│   ├── GoogleSignInButton.tsx
│   ├── form-message.tsx
│   └── submit-button.tsx
├── middleware.ts
├── actions.ts
└── utils/
    └── supabase/
        ├── client.ts
        ├── middleware.ts
        └── server.ts
```

## 3. 기본 제공 기능

### 3.1 인증 관련

- ✅ 미들웨어 기반 인증 보호
- ✅ 서버 사이드 세션 관리
- ✅ Supabase Auth Helpers
- ✅ TypeScript 타입 지원

### 3.2 데이터베이스 연동

- ✅ Supabase 클라이언트 설정
- ✅ 서버 컴포넌트 지원
- ✅ 실시간 구독 지원

## 4. 추가된 기능

### 4.1 인증 시스템

- ✅ 이메일/비밀번호 회원가입
- ✅ 이메일/비밀번호 로그인
- ✅ Google OAuth 로그인
- ✅ 비밀번호 재설정
- ✅ 로그아웃

### 4.2 사용자 인터페이스

- ✅ 다크 테마 적용
- ✅ 반응형 디자인
- ✅ Google 로그인 버튼 커스텀 디자인
- ✅ 로딩 상태 표시
- ✅ 에러 메시지 표시

## 5. 환경 설정

### 5.1 환경 변수 설정

```env
NEXT_PUBLIC_SUPABASE_URL=your-project-url
NEXT_PUBLIC_SUPABASE_ANON_KEY=your-anon-key
```

### 5.2 개발 서버 실행

```bash
npm run dev
```

## 6. 향후 개선사항

### 6.1 추가 기능

- ⬜️ 사용자 프로필 관리
- ⬜️ 소셜 로그인 추가
- ⬜️ 이메일 인증 프로세스
- ⬜️ 세션 관리 개선

### 6.2 성능 최적화

- ⬜️ 이미지 최적화
- ⬜️ 코드 스플리팅
- ⬜️ 캐싱 전략 구현

## 7. 시스템 요구사항

- Node.js 18.x 이상
- npm 9.x 이상
- Git
- VS Code (권장)
