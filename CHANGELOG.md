# Changelog

All notable changes to this project will be documented in this file.

## [1.0.0] - 2025-09-25

### Added
- **Initial Release**: Mindful Motion 요가 스튜디오 웹사이트
- **Landing Page**: 메인 홈페이지 (`index.html`)
  - 히어로 섹션 with 배경 이미지
  - 6개 요가 클래스 카드 (Hatha, Vinyasa, Restorative, Power, Yin, Hot Yoga)
  - 시설 및 서비스 소개 섹션
  - 예약 및 위치 안내 섹션
  - 푸터 with 상세 정보

- **Booking System**: 예약 시스템 (`booking.html`)
  - 완전한 예약 폼 (이름, 연락처, 이메일, 클래스 선택, 경험 수준, 희망 날짜, 메시지)
  - 클라이언트 사이드 유효성 검사
  - Discord 웹훅 연동으로 실시간 알림
  - 환경변수 기반 웹훅 URL 관리

- **Location Page**: 위치 안내 페이지 (`location.html`)
  - 상세 위치 정보
  - 교통편 안내
  - 구글맵 연동

- **Privacy Policy**: 개인정보 처리방침 (`privacy.html`)
  - GDPR 준수 개인정보 처리방침
  - 상세한 데이터 처리 정책

- **Design System**: 디자인 시스템
  - 웜 브라운 컬러 팔레트
  - Tailwind CSS 기반 반응형 디자인
  - 커스텀 favicon (요가 포즈 SVG)
  - 호버 효과 및 애니메이션
