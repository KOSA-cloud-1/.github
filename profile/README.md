# Hybrid Infrastructure Project

## 프로젝트 개요

본 프로젝트는 On-Premise와 AWS를 결합한 Hybrid Infrastructure를 구축하여 다음을 목표로 합니다.

* Cost Optimization (비용 절감)
* Performance Scalability (성능 확장)
* High Availability (고가용성)

---

## 아키텍처

* On-Premise: Proxmox + Kubernetes + Ceph
* Cloud: AWS (Entry Point + Scaling)
* Network: VPN 기반 연결

---

## 전략

### Cost Optimization

* 기본 워크로드는 On-Premise에서 처리
* AWS는 필요 시에만 사용

### Performance

* Kubernetes 기반 Horizontal Scaling
* HAProxy + Ingress 기반 트래픽 분산

---

## Repository 구성

* app
* docs
* kubernetes-manifest
* infra-aws
* infra-proxmox

---

## 기여 방법

아래 문서를 참고하세요:

→ `.github/CONTRIBUTING.md`

