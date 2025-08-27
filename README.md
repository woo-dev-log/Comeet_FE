# COMEET
위치 기반으로 주변 개발자들을 발견하고 연결하는 지역형 개발자 커뮤니티입니다.

## 프로젝트 배경
기존 개발자 커뮤니티의 한계점을 해결하고자 시작한 프로젝트입니다!</br>
온라인 중심의 소통을 넘어 **실제 만날 수 있는 거리의 개발자들과의 오프라인 연결**에 초점을 맞춰 설계했습니다.

### 프로젝트 목적
- **위치 기반 필터링**으로 반경 1~10km 내 개발자 탐색
- **GitHub 연동**을 통한 투명한 기술 스택과 활동 지표 공개
- **목적별 게시판**으로 프로젝트 모집, 모각코, 질문 게시 지원
- **실시간 채팅**으로 즉석 만남과 협업 조율

**해결하고자 한 문제들**
- 온라인 커뮤니티의 오프라인 연결 한계 → **위치 기반 개발자 탐색**
- 수도권 편중된 개발자 모임 → **지역별 생태계 활성화**
- 허위 프로필과 신뢰성 부족 → **GitHub 연동 검증 시스템**

## 아키텍처 & 기술적 도전
### 위치 기반 탐색 시스템
반경별 필터링으로 실시간 탐색 경험을 제공합니다.

### GitHub OAuth
**GitHub API v4**을 활용한 실시간 개발 활동 동기화 시스템으로 사용자의 정보를 수집합니다.

### 하이브리드 상태 관리
**TanStack Query + Zustand** 조합으로 서버 상태(위치, 프로필)와 클라이언트 상태(필터, UI)를 분리 관리했습니다.

## 기능별 스크린샷
<table>
<tr>
<td width="50%">

### GitHub OAuth 로그인
- GitHub 계정 연동으로 개발자 신원 확인
- 실제 개발 활동 기반 프로필 생성
<img width="175" height="400" alt="image" src="https://github.com/user-attachments/assets/31b1e9dc-775c-4f17-adf5-034a9df28e23" />
</td>
<td width="50%">

### 위치 기반 개발자 탐색
- **거리별 필터링**: 1km/3km/5km/10km 선택
- **리스트 뷰**: 거리순, 활동도순, 스택 매칭도순 정렬
<img width="250" height="333" alt="스크린샷 2025-08-27 오후 9 01 26" src="https://github.com/user-attachments/assets/9840baa8-db7e-41bb-b3ca-c839a73d2b03" />
</td>
</tr>
<tr>
<td width="50%">

### 프로젝트 모집 게시판
- **역할별 모집**: 개발, 인프라, 데이터, 기획/디자인 등
- **기술 스택 필터**: React, Node.js, Python 등
<img width="287" height="339" alt="스크린샷 2025-08-27 오후 9 03 48" src="https://github.com/user-attachments/assets/b22e9dd5-e0f0-4c9c-9d04-a90c93f9710f" />
</td>
<td width="50%">

### 실시간 메시징
- **1:1 DM**: 프로필/게시글에서 바로 대화 시작
- **알림 시스템**: 새 메시지, 모임 리마인더
<img width="358" height="397" alt="스크린샷 2025-08-27 오후 9 04 29" src="https://github.com/user-attachments/assets/3d9a3a64-16fd-4d75-85f3-ba3bd96f715c" />
</td>
</tr>
</table>

## Tech Stack
### Frontend
```json
{
  "framework": "React + TypeScript",
  "styling": "Tailwind CSS",
  "state": "TanStack Query"
}
```

### Backend
```json
{
  "framework": "NestJS + TypeScript",
  "database": "PostgreSQL + TypeORM",
  "auth": "JWT + GitHub OAuth",
  "cache": "Valkkey (Redis-compatible)"
}
```

Infrastructure & DevOps
```json
{
  "server": "Amazon EC2",
  "containerization": "Docker",
  "reverse_proxy": "NGINX", 
  "ci_cd": "GitHub Actions",
  "monitoring": "로그 수집 + 헬스체크"
}
```

## 개발 프로세스
### Git 브랜치 전략
- **main**: 프로덕션 배포 브랜치
- **develop**: 통합 개발 브랜치
- **feature/**: 기능별 개발 브랜치

### 4주 개발 스프린트
- **1주차**: 아키텍처 설계, GitHub OAuth, 기본 UI
- **2주차**: 위치 시스템, 프로필 관리, API 연동
- **3주차**: 게시판, 메시징 시스템
- **4주차**: 성능 최적화, 접근성, QA 및 배포
