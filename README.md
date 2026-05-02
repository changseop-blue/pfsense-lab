# 🛡️ pfSense-Lab

> 가상화 환경(VMware) 기반 **pfSense 방화벽 구축 및 네트워크 보안 실습** 저장소

![pfSense](https://img.shields.io/badge/pfSense-CE-212121?logo=pfsense&logoColor=white)
![VMware](https://img.shields.io/badge/VMware-Workstation%2025H2-607078?logo=vmware&logoColor=white)
![Status](https://img.shields.io/badge/status-In%20Progress-brightgreen)
![License](https://img.shields.io/badge/license-MIT-blue)

---

## 📌 프로젝트 개요

오픈소스 방화벽 **pfSense**를 활용해 네트워크 보안 환경을 직접 설계·구축·검증한 실습 기록입니다.
WAN/LAN 분리, 방화벽 정책, NAT, IDS/IPS, VPN, 로그 분석까지 **네트워크 보안 실무에서 요구되는 핵심 영역**을 단계별로 다룹니다.

### 🎯 학습 목표
- 가상화 환경에서 안전한 네트워크 세그먼트 설계 및 분리
- 방화벽 룰셋과 NAT 정책을 통한 트래픽 제어 메커니즘 이해
- IDS/IPS·VPN 등 보안 패키지의 통합 운용 능력 확보
- 로그 기반 이상 트래픽 탐지 및 대응 절차 숙지

---

## 🧰 실습 환경

| 구분 | 사용 기술 |
| :--- | :--- |
| 가상화 플랫폼 | VMware Workstation Full 25H2u1 (Build 25219725) |
| 방화벽 OS | pfSense Community Edition |
| 내부 호스트 | Rocky Linux / AlmaLinux, Windows 10 |
| 보안 패키지 | Suricata, pfBlockerNG, OpenVPN |
| 분석 도구 | Wireshark, nmap, tcpdump |

---

## 📚 실습 로드맵 및 현황

| 단계 | 실습 주제 | 진행 상태 | 주요 내용 및 목표 |
| :---: | :--- | :---: | :--- |
| **01** | 네트워크 및 기본 환경 구성 | 🟢 진행 중 | WAN/LAN 인터페이스 설정, DHCP, 기본 라우팅 |
| **02** | 방화벽 규칙 및 NAT 설정 | ⚪ 예정 | 인/아웃바운드 트래픽 제어, 포트 포워딩, 1:1 / 다대다 NAT |
| **03** | 보안 패키지 및 위협 탐지 | ⚪ 예정 | Suricata IDS/IPS, pfBlockerNG, 시그니처 튜닝 |
| **04** | VPN 및 원격 접속 | ⚪ 예정 | OpenVPN / IPsec 기반 안전한 원격 접속 환경 구축 |
| **05** | 로그 분석 및 모니터링 | ⚪ 예정 | System Log 분석, SIEM(Wazuh / ELK) 연동 테스트 |

> ✅ 완료 · 🟢 진행 중 · ⚪ 예정

---

## 📂 디렉토리 구조

```text
pfSense-Lab/
├── README.md
├── .gitignore
│
├── 01-basic-network/          # 기본 네트워크 환경 구성
│   ├── README.md
│   └── images/
│
├── 02-firewall-nat/           # 방화벽 규칙 및 NAT
│   ├── README.md
│   └── images/
│
├── 03-ids-ips/                # Suricata / pfBlockerNG
│   ├── README.md
│   └── images/
│
├── 04-vpn/                    # OpenVPN / IPsec
│   ├── README.md
│   └── images/
│
├── 05-monitoring/             # 로그 및 SIEM 연동
│   ├── README.md
│   └── images/
│
├── docs/
│   ├── network-topology.md    # 전체 네트워크 토폴로지
│   └── firewall-rules.md      # 통합 방화벽 / NAT 룰셋
│
└── configs/                   # 설정 백업 (민감정보 제거 후 업로드)
    └── ...
```

---

## 🗺️ 네트워크 토폴로지

> 자세한 구성도는 [`docs/network-topology.md`](docs/network-topology.md) 참조

```text
        [ Internet ]
             │
          (WAN)
             │
       ┌───────────┐
       │  pfSense  │
       └───────────┘
        │         │
      (LAN)     (DMZ)
        │         │
 [Internal Hosts] [Web / DB Server]
```

---

## 📝 실습 노트

- [ ] **01.** pfSense 설치 및 초기 콘솔 설정
- [ ] **02.** WAN / LAN 인터페이스 구성 및 DHCP 활성화
- [ ] **03.** 인바운드 / 아웃바운드 방화벽 규칙 작성
- [ ] **04.** NAT 및 포트 포워딩 시나리오 검증
- [ ] **05.** Suricata 설치 및 IDS / IPS 룰셋 적용
- [ ] **06.** OpenVPN 원격 접속 환경 구축
- [ ] **07.** 시스템 로그 수집 및 이상 트래픽 분석

---

## 🔒 보안 고지

본 저장소에 포함된 IP 주소, 도메인, 인증서는 모두 **실습 환경의 더미 값**입니다.
공개된 설정 백업 파일은 비밀번호 해시, 인증서, VPN 키 등 **민감 정보가 제거된 상태(sanitized)** 로 업로드되었습니다.

---

## 📖 참고 자료

- [pfSense 공식 문서](https://docs.netgate.com/pfsense/en/latest/)
- [Suricata User Guide](https://suricata.readthedocs.io/)
- [pfBlockerNG 공식 가이드](https://docs.netgate.com/pfsense/en/latest/packages/pfblocker.html)
- KISA, *주요정보통신기반시설 기술적 취약점 분석·평가 방법 상세가이드*

---

## 👤 작성자

| 항목 | 내용 |
| :--- | :--- |
| 작성자 | 이창섭 |
| 학습 목적 | 정보보안산업기사 과정평가형 실습 포트폴리오 |
| 학습 기간 | 2026.05 ~ 진행 중 |
| 연락처 | _작성 예정_ |
