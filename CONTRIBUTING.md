# Contributing Guide

## 1. Branch Strategy

프로젝트의 안정성과 협업 효율을 위해 다음 브랜치 전략을 사용합니다.

* main: 항상 배포 가능한 상태 (stable)
* dev: 개발 통합 브랜치 (모든 레포 공통)

---

### Branch Naming 규칙

* feature/<name> : 새로운 기능 개발
* fix/<name> : 버그 수정
* docs/<name> : 문서 작업
* infra/<name> : 인프라 작업 (AWS, Proxmox, Terraform 등)
* chore/<name> : 기타 정리 작업
* hotfix/<name> : 긴급 수정

예시:

feature/add-login-api
fix/ingress-timeout
infra/aws-vpn-setup

---

## 2. Workflow

모든 작업은 아래 흐름을 따릅니다.

feature/* → dev → main
fix/*     → dev → main

설명:

1. feature 또는 fix 브랜치에서 작업
2. dev 브랜치로 Pull Request
3. 테스트 및 검증
4. main 브랜치로 최종 merge

---

## 3. Commit Convention

커밋 메시지는 아래 형식을 따릅니다.

type: description

---

### type 종류

* feat: 기능 추가
* fix: 버그 수정
* docs: 문서 변경
* refactor: 코드 리팩토링
* test: 테스트 코드
* chore: 기타 작업
* infra: 인프라 변경 (Terraform, AWS, Proxmox 등)
* ci: CI/CD 설정

---

### 예시

feat: 사용자 로그인 기능 추가
fix: ingress 라우팅 문제 수정
infra: aws vpn 구성 추가

---

## 4. Pull Request 규칙

* 모든 변경 사항은 Pull Request(PR)로만 merge
* main 브랜치 직접 push 금지

---

### PR 제목 규칙

Commit Convention과 동일하게 작성

예시:

feat: 상품 서비스 배포 추가

---

## 5. Merge Strategy

* Squash and Merge 사용
* 커밋 히스토리를 깔끔하게 유지

---

## 6. Code Review

* 최소 1명 이상의 approve 필요

리뷰 시 확인:

* 정상 동작 여부
* 코드/구성 일관성
* 인프라 영향도

---

## 7. 공통 규칙

* 작은 단위로 commit
* 의미 있는 commit message 작성
* 변경 시 문서 반드시 업데이트

