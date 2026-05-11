# Contributing Guide

## 1. Branch Strategy

프로젝트의 안정성과 협업 효율을 위해 **Git Flow 기반 브랜치 전략**을 사용합니다.

* `main`: 항상 배포 가능한 안정 브랜치 (production)
* `dev`: 개발 통합 브랜치 (integration)
* `feature/*`: 기능 개발 및 일반 작업 브랜치
* `release/*`: 배포 준비 브랜치
* `hotfix/*`: 운영 환경 긴급 수정 브랜치

---

### Branch Naming 규칙

작업 브랜치는 다음 형식을 사용합니다.

* `feature/<name>`: 기능 개발, 문서 수정, 인프라 작업 등 일반 작업
* `release/<version>`: 배포 준비
* `hotfix/<name>`: 긴급 수정

예시:

```text
feature/add-login-api
feature/update-docs-readme
feature/setup-aws-vpn
release/v1.0.0
hotfix/ingress-timeout
```

---

## 2. Workflow

모든 작업은 아래 Git Flow를 따릅니다.

```text
feature/*  → dev
release/*  → main, dev
hotfix/*   → main, dev
```

---

### 작업 흐름

1. `dev` 브랜치에서 `feature/*` 브랜치를 생성합니다.
2. 기능 개발 및 작업을 수행합니다.
3. `feature/*` → `dev`로 Pull Request를 생성합니다.
4. 코드 리뷰 및 테스트를 진행합니다.
5. 모든 기능이 통합되면 `release/*` 브랜치를 생성합니다.
6. 배포 전 최종 검증을 수행합니다.
7. `release/*` → `main`으로 merge하여 배포합니다.
8. 동일한 변경사항을 `dev`에도 반영합니다.

---

### Hotfix 흐름

1. `main` 브랜치에서 `hotfix/*` 브랜치를 생성합니다.
2. 긴급 수정 작업을 수행합니다.
3. `hotfix/*` → `main`으로 merge합니다.
4. 동일한 변경사항을 `dev`에도 반영합니다.

---

## 3. Commit Convention

커밋 메시지는 아래 형식을 따릅니다.

```text
type: description
```

---

### type 종류

* `feat`: 기능 추가
* `fix`: 버그 수정
* `docs`: 문서 변경
* `refactor`: 코드 리팩토링
* `test`: 테스트 코드
* `chore`: 기타 작업
* `infra`: 인프라 변경 (Terraform, AWS, Proxmox 등)
* `ci`: CI/CD 설정

---

### 예시

```text
feat: 사용자 로그인 기능 추가
fix: ingress 라우팅 문제 수정
infra: aws vpn 구성 추가
```

---

## 4. Pull Request 규칙

* 모든 변경 사항은 Pull Request(PR)로만 merge합니다.
* `main`, `dev` 브랜치에 직접 push를 금지합니다.
* PR은 반드시 적절한 대상 브랜치(`dev` 또는 `main`)로 생성합니다.
* Self merge는 지양합니다.

---

### PR 제목 규칙

Commit Convention과 동일하게 작성합니다.

예시:

```text
feat: 상품 서비스 배포 추가
```

---

## 5. Merge Strategy

* **Squash and Merge** 전략을 사용합니다.
* 커밋 히스토리를 간결하게 유지합니다.

---

## 6. Code Review

* 최소 1명 이상의 approve가 필요합니다.

리뷰 시 확인 사항:

* 정상 동작 여부
* 코드 및 인프라 구성 일관성
* 변경 사항의 영향 범위

---

## 7. 공통 규칙

* 작은 단위로 commit 합니다.
* 의미 있는 commit message를 작성합니다.
* 변경 사항 발생 시 관련 문서를 반드시 업데이트합니다.

---

## 8. Branch Protection

다음 브랜치에는 보호 규칙을 적용합니다.

### main

* direct push 금지
* Pull Request 필수
* 최소 1명 이상의 승인 필요

### dev

* direct push 금지
* Pull Request 필수
```

---

