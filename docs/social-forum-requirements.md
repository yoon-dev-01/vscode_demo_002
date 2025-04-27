# 소셜 포럼 애플리케이션 PRD

## 1. 프로젝트 개요

### 1.1 프로젝트 목적

- 사용자 간의 자유로운 토론과 정보 공유를 위한 소셜 포럼 플랫폼
- 실시간 상호작용이 가능한 커뮤니티 공간 제공
- 주제별 카테고리를 통한 체계적인 콘텐츠 관리

### 1.2 기술 스택

- Frontend: Next.js 14, TypeScript, Tailwind CSS
- Backend: Supabase (데이터베이스, 인증, 실시간 기능)
- 배포: Vercel

## 2. 핵심 기능

### 2.1 사용자 관리

- ⬜️ 이메일/소셜 로그인 (Google, GitHub)
- ⬜️ 사용자 프로필 관리
- ⬜️ 팔로우/팔로잉 시스템
- ⬜️ 활동 기록 및 통계

### 2.2 게시물 관리

- ⬜️ 게시물 CRUD 작업
- ⬜️ 마크다운 에디터 지원
- ⬜️ 이미지/파일 업로드
- ⬜️ 태그 시스템
- ⬜️ 게시물 검색 기능

### 2.3 상호작용

- ⬜️ 댓글 시스템
- ⬜️ 좋아요/북마크
- ⬜️ 실시간 알림
- ⬜️ 게시물 공유

### 2.4 카테고리/주제

- ⬜️ 메인 카테고리 관리
- ⬜️ 서브 카테고리 시스템
- ⬜️ 인기 주제 추적
- ⬜️ 맞춤 피드 제공

## 3. 데이터베이스 구조

### 3.1 주요 테이블

```sql
-- 사용자
users (
  id uuid primary key,
  username text unique,
  email text unique,
  avatar_url text,
  created_at timestamp with time zone
)

-- 게시물
posts (
  id uuid primary key,
  title text,
  content text,
  author_id uuid references users,
  category_id uuid references categories,
  created_at timestamp with time zone
)

-- 댓글
comments (
  id uuid primary key,
  content text,
  post_id uuid references posts,
  author_id uuid references users,
  created_at timestamp with time zone
)

-- 카테고리
categories (
  id uuid primary key,
  name text,
  slug text unique,
  parent_id uuid references categories
)
```

## 4. UI/UX 요구사항

### 4.1 레이아웃

- ⬜️ 반응형 디자인
- ⬜️ 다크/라이트 테마
- ⬜️ 사이드바 네비게이션
- ⬜️ 모바일 최적화

### 4.2 주요 페이지

- ⬜️ 홈/피드 페이지
- ⬜️ 게시물 상세 페이지
- ⬜️ 사용자 프로필 페이지
- ⬜️ 카테고리/태그 페이지
- ⬜️ 검색 결과 페이지

## 5. 성능 요구사항

### 5.1 로딩 성능

- 초기 페이지 로드: < 2초
- 게시물 로딩: < 1초
- 이미지 최적화 적용

### 5.2 실시간 성능

- 댓글 동기화: < 500ms
- 알림 전달: < 1초

## 6. 보안 요구사항

- ⬜️ HTTPS 적용
- ⬜️ XSS 방어
- ⬜️ CSRF 보호
- ⬜️ 레이트 리미팅
- ⬜️ 입력값 검증

## 7. 배포 계획

### 7.1 개발 단계

1. 기본 CRUD 기능 구현
2. 사용자 인증 시스템
3. 실시간 기능 추가
4. UI/UX 개선
5. 성능 최적화

### 7.2 모니터링

- ⬜️ 에러 추적
- ⬜️ 성능 모니터링
- ⬜️ 사용자 행동 분석
- ⬜️ 시스템 헬스 체크

## 8. 시스템 요구사항

- Node.js 18.x 이상
- PostgreSQL 14.x 이상
- Redis (선택사항)
- 최신 웹 브라우저 지원
