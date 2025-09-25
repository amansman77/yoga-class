# Cloudflare Pages 배포 가이드

## 🚀 배포 방법

### 1. GitHub 연동 배포 (권장)

1. **GitHub 저장소 생성**
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/your-username/yoga-class.git
   git push -u origin main
   ```

2. **Cloudflare Pages 설정**
   - Cloudflare 대시보드 → Pages → "Create a project"
   - "Connect to Git" 선택
   - GitHub 저장소 연결
   - 프로젝트 이름: `yoga-class`
   - 프레임워크: "None" (Static Site)
   - 빌드 명령어: (비워둠)
   - 빌드 출력 디렉토리: `/` (루트)

### 2. 직접 업로드 배포

1. **파일 압축**
   ```bash
   zip -r yoga-class.zip . -x "*.git*" "node_modules/*"
   ```

2. **Cloudflare Pages 업로드**
   - Cloudflare 대시보드 → Pages → "Upload assets"
   - 압축 파일 업로드

## ⚙️ 설정 파일 설명

### `_headers`
- 보안 헤더 설정
- 캐시 정책 설정
- 정적 자산 최적화

### `_redirects`
- URL 리다이렉트 규칙
- SPA 라우팅 지원
- 404 처리

### `wrangler.toml`
- Cloudflare Workers/Pages 설정
- 환경 변수 설정
- 빌드 설정

### `package.json`
- 프로젝트 메타데이터
- 스크립트 명령어
- 의존성 관리

## 🔧 환경 변수 설정

Cloudflare Pages 대시보드에서 다음 환경 변수 설정:

```
NODE_ENV=production
ENVIRONMENT=production
```

## 📱 도메인 설정

1. **커스텀 도메인 연결**
   - Pages 프로젝트 → Settings → Domains
   - 도메인 추가 및 DNS 설정

2. **SSL 인증서**
   - 자동으로 Let's Encrypt 인증서 발급
   - HTTPS 강제 리다이렉트 설정

## 🚀 배포 후 확인사항

- [ ] 모든 페이지 정상 로딩
- [ ] 예약 폼 Discord 연동 테스트
- [ ] 모바일 반응형 확인
- [ ] 이미지 최적화 확인
- [ ] 페이지 속도 테스트

## 🔄 환경변수 설정

1. **Discord 웹훅 URL 설정:**
   - Pages 대시보드에서 "Settings" → "Environment variables" 클릭
   - "Add variable" 클릭
   - **Name:** `DISCORD_WEBHOOK_URL`
   - **Value:** `https://discord.com/api/webhooks/blah`
   - "Save" 클릭

## 🔄 자동 배포 설정

GitHub에 푸시할 때마다 자동 배포되도록 설정:

1. **GitHub Actions** (선택사항)
2. **Cloudflare Pages 자동 빌드** (기본 제공)

## 📊 성능 최적화

- **이미지 최적화**: WebP 형식 사용 권장
- **CDN**: Cloudflare 글로벌 CDN 자동 적용
- **캐싱**: 정적 자산 1년 캐시 설정
- **압축**: Gzip/Brotli 자동 압축
