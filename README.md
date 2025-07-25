# React + Flask Blog CMS Platform

## 프로젝트 개요

이 프로젝트는 React 기반 블로그 템플릿을 클론 코딩하고, Flask를 백엔드로 사용하여 실제 운영 가능한 블로그 CMS 플랫폼으로 확장하는 것을 목표로 합니다.  
**관리자 전용 CMS 대시보드**를 통해 블로그 글 작성과 내가 개발한 서비스들을 통합 관리할 수 있도록 설계되어 있습니다.  
일반 사용자는 글 열람만 가능하며, 모든 콘텐츠 및 시스템 관리는 **관리자만 접근 가능한 CMS에서 수행**됩니다.

---

## 개발 단계 (로드맵)

### 1차: 블로그 프론트엔드 개발 및 관리자 CMS UI

- React 기반 UI 개발
- 블로그 기능 구성
  - 글 목록, 상세 보기
  - 카테고리 및 검색
- 관리자 CMS 대시보드
  - 로그인
  - 블로그 글 작성 / 수정 / 삭제
  - 내 서비스 관리용 UI (통합 모니터링, 설정 등)

### 2차: 백엔드 서버 구축 (Flask + MYSQL)

- Flask REST API 구성
  - 블로그 CRUD
  - 관리자 로그인/로그아웃
- 세션 + 쿠키 기반 인증
- DB: MYSQL
- 파일 업로드 처리
- 인증 미들웨어 구성

### 3차: CMS 확장

- 자체 서비스 관리 기능 추가
- 관리자 권한 분리 및 접근 제어
- 비공개 / 비밀글 기능

### 4차: 보안 기능 및 WAF 구축

- OWASP top 10 기반하여 WAF를 개발할 예정 입니다.
- WAF는 AI를 이용하여 개발할 예정입니다.

---

## 사용 기술

| 범주       | 기술 스택                     |
| ---------- | ----------------------------- |
| 프론트엔드 | React, React Router, JSX, CSS |
| 백엔드     | Python,- MYSQL                |
| 인증       | 세션 + 쿠키 기반 인증         |
| 배포       | GCP , Docker 기반 분리        |

---

## Docker & 배포

- 프론트엔드와 백엔드는 **Docker 컨테이너로 분리**하여 관리합니다.
- GCP(Google Cloud Platform) 환경에 배포예정이며, `Docker Compose`를 통해 로컬 및 클라우드에서 통합 테스트 가능합니다.

### 1. Docker 이미지 빌드 및 실행

```bash
# 프론트엔드
cd client
docker build -t blog-frontend .
docker run -p 3000:3000 blog-frontend

# 백엔드
cd server
docker build -t blog-backend .
docker run -p 5000:5000 blog-backend
```

### 2. Docker Compose (예정)

`docker-compose.yml`을 이용해 프론트/백 통합 실행 환경 구성 예정입니다.

---

## 설치 및 로컬 실행 (개발용)

### 프론트엔드

```bash
cd client
npm install
npm start
```

### 백엔드 (Flask)

```bash
cd server
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
python app.py
```

---

## 개발자 노트

- 본 프로젝트는 **React + Flask 기반 블로그 CMS**입니다.
- 콘텐츠 작성 및 서비스 관리는 **관리자 대시보드(CMS)**를 통해 수행됩니다.
- 프론트/백엔드는 Docker로 분리되어 있으며, GCP에 배포됩니다.

---
