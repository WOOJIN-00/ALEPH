# IT 인프라 및 네트워크/정보보안 기초 정리 Guide

제공해주신 학습 노트를 바탕으로 개념을 체계적으로 구조화하고, 부족한 이론적 배경과 기술적 상세 설명을 추가하여 확장한 최종 표준 정리 문서입니다.

---

## 1. 클라이언트 - 서버 모델 (Client-Server Architecture)

네트워크 아키텍처의 가장 기본적인 작동 방식으로, 서비스 요청자와 제공자의 역할 분담을 정의합니다.

* **클라이언트 (Client, 정보 요청자):** 서비스나 리소스를 요청하는 엔드포인트(웹 브라우저, 모바일 앱, PC 등)입니다.
* **서버 (Server, 정보 제공자):** 클라이언트의 요청을 받아 처리하고, 처리된 결과나 데이터를 응답으로 제공하는 시스템(웹 서버, DB 서버, 파일 서버 등)입니다.

---

## 2. IT 인프라 요소 및 서비스 모델 (IT Infrastructure)

### 2.1 클라우드 컴퓨팅 서비스 분류 (Cloud Services)
인터넷 네트워크를 통해 온디맨드(On-Demand)로 컴퓨팅 자원을 이용하는 환경입니다. 주요 서비스 모델은 다음과 같이 구분됩니다.

* **SaaS (Software as a Service - 서비스형 소프트웨어):**
  * 완성된 애플리케이션 형태 서비스 (예: Google Workspace, Microsoft 365, Notion).
  * 사용자는 별도의 설치나 관리 없이 웹/앱을 통해 바로 사용.
* **PaaS (Platform as a Service - 서비스형 플랫폼):**
  * 애플리케이션 개발 및 실행에 필요한 개발 환경(OS, 미들웨어, 런타임 등)을 제공.
* **IaaS (Infrastructure as a Service - 서비스형 인프라):**
  * 서버, 저장소, 네트워크 등 기초 물리/가상 인프라 자원을 제공 (예: AWS EC2, GCP Compute Engine).

*(참고: 작성해주신 'SASS, SLD'는 구름/클라우드 관련 내용에서 **SaaS, PaaS, IaaS** 및 아키텍처 문서용 **SLD(Single Line Diagram, 단선도)** 개념과 연관됩니다.)*

---

## 3. 정보보안의 정의 및 3대 요소 (Information Security)

정보보안은 관리적, 물리적, 기술적 통제를 통해 정보 자산을 위협으로부터 보호하는 모든 활동을 의미합니다.

### 3.1 정보보안의 3대 요소 (CIA Triad)
* **기밀성 (Confidentiality):** 인가된 사용자만 정보에 접근할 수 있도록 보장 (암호화, 접근 제어 등).
* **무결성 (Integrity):** 정보가 위·변조되지 않고 정확성과 완전성이 유지됨을 보장 (해시 함수, 디지털 서명 등).
* **가용성 (Availability):** 인가된 사용자가 필요할 때 언제든 정보 및 시스템에 접근하여 이용할 수 있음을 보장 (이중화, 백업, DDoS 방어 등).

### 3.2 정보보안 3대 영역 (통제 체계)
1. **물리적 보안:** 출입 통제 시스템, 보안 울타리, CCTV, 내진/소방 설비, 자원 실물 보호.
2. **관리적 보안:** 보안 정책/지침 수립, 인적 보안 관리(보안 교육, 퇴사자 권한 회수), BCP/DRP(업무 연속성 계회).
3. **기술적 보안:** 접근 통제, 네트워크 방화벽, 암호화, 시스템 침입 탐지/방지, 웹 보안 설정 등.

---

## 4. 영역별 보안 기술 분야 (Security Domains)

### 4.1 네트워크 보안 (Network Security)
* **기본 기술:** 스위칭(L2/L3 Switching), 라우팅(Routing), L3/L4 접근제어정책(ACL - Access Control List).
* **주요 장비 및 솔루션:**
  * **Firewall (방화벽):** IP/Port 기반으로 네트워크 트래픽을 필터링하여 인가된 요청만 허용.
  * **VPN (Virtual Private Network, 가상사설망):** 공용망을 암호화 터널링하여 전용선처럼 안전하게 연결.
  * **NAT (Network Address Translation):** 사설 IP 주소를 공인 IP 주소로 변환하여 IP 부족 해결 및 내부망 은닉.
  * **IDS / IPS (Intrusion Detection/Prevention System):** 네트워크 침입을 탐지(IDS) 및 차단(IPS).
  * **NMS (Network Management System):** 네트워크 장비의 상태, 성능, 트래픽을 실시간 모니터링 및 관리.
  * **DDoS 대응 솔루션:** 과도한 정상/기능성 트래픽 유입 공격을 분석하고 정화/차단.

### 4.2 시스템 보안 (System Security)
* **서버 구축 및 보안 설정:** OS(Linux/Windows) 계정 관리, 권한 설정, 서비스 최소화, 패치 관리.
* **Buffer Overflow (BoF) 공격 대응:** 메모리 버퍼 경계를 초과하는 데이터를 주입해 악성 코드를 실행하는 공격을 방지 (ASLR, DEP 기술 등 적용).
* **Log 관리:** 감사 로그(Audit Log), 접속 로그, 시스템 로그 수집 및 분석 (SIEM 연동).
* **쉘 스크립트 (Shell Scripting):** 보안 점검 자동화, 로그 분석 자동화, 서버 설정 일괄 적용.

### 4.3 웹 보안 (Web Security)
* **웹 공격 탐지 및 로그 분석:** SQL Injection, XSS, CSRF, File Upload 취약점 등 분석.
* **OWASP (Open Web Application Security Project):** 웹 애플리케이션 보안 취약점 표준 연구 단체 (OWASP Top 10 제공).
* **모의해킹 (Penetration Testing) 및 워게임 (Wargame):** 실무 시스템에 악의적 공격 기법을 시뮬레이션하여 취약점을 점검하고 방어 방안 마련.
* **CTF (Capture The Flag):** 해킹 기법을 바탕으로 문제 속 플래그(Flag)를 찾는 보안 경진대회.

---

## 5. 네트워크 계층 및 주소 체계 (OSI 7 계층 & TCP/IP)

### 5.1 표준화 기구
* **ISO (International Organization for Standardization):** OSI 7계층 참조 모델을 제정한 국제 표준화 기구.

### 5.2 전송 매체 및 연결 장치
* **UTP 케이블:** 물리 계층(L1)에서 신호를 전달하는 가장 흔한 트위스티드 페어 케이블.
* **RJ-45 잭 (AJ-45):** UTP 케이블 끝단에 결합하여 랜카드나 스위치 포트에 연결하는 커넥터 규격.

### 5.3 계층별 식별 주소 (Addressing Scheme)
| 계층 | 대표 주소 | 설명 |
| :--- | :--- | :--- |
| **L2 (데이터 링크 계층)** | **MAC 주소** | 하드웨어 고유 주소 (랜카드 제조 시 부여되는 물리적 주소, 예: `00:1A:2B:3C:4D:5E`) |
| **L3 (네트워크 계층)** | **IP 주소** | 로지컬(논리적) 주소 (네트워크상에서 위치를 식별하기 위해 부여, 예: `192.168.0.1`) |
| **L4 (전송 계층)** | **Port 주소** | 프로세스/서비스 식별 주소 (호스트 내에서 실행 중인 애플리케이션 구분, 예: HTTP=80, HTTPS=443) |

### 5.4 전송 프로토콜 (Transport Protocols)
네트워크상에서 데이터를 전송할 때 택배 배달원 역할을 담당하며, **TCP와 IP가 조합(TCP/IP)**되어 데이터가 정확한 목적지로 배달됩니다.

* **TCP (Transmission Control Protocol):**
  * **연결 지향적 프로토콜**로, 신뢰성 있는 데이터 전송을 보장.
  * **3-Way Handshaking**을 통해 연결을 설정하고, **4-Way Handshaking**을 통해 연결을 해제.
  * 순서 제어, 흐름 제어, 혼잡 제어를 수행.
* **UDP (User Datagram Protocol):**
  * **비연결 지향적 프로토콜**로, 수신 여부를 확인하지 않고 전송.
  * 오버헤드가 적고 속도가 빠름.
  * **실시간 스트리밍, 온라인 게임, DNS 요청, VoIP** 등 빠른 전송이 중요한 분야에 사용.
* **PTP / NTP:** 네트워크 장비 간 정확한 시각 동기화를 위한 시간 프로토콜 (Precision Time Protocol).

---

## 6. 주요 네트워크 진단 CMD 명령어 및 ICMP 프로토콜

Windows 및 Linux 명령 프롬프트(CMD)에서 사용하는 네트워크 상태 확인 및 문제 해결 명령어입니다.

### 6.1 네트워크 진단 명령어
* **`arp -a`:**
  * ARP(Address Resolution Protocol) 캐시 테이블을 조회.
  * 현재 통신한 장비들의 **IP 주소를 MAC 주소로 변환/매핑된 내역**을 출력.
* **`ipconfig /all`:**
  * 호스트의 모든 네트워크 어댑터 정보(IP 주소, 서브넷 마스크, 게이트웨이, MAC 주소, DNS 서버 등)를 상세 출력.
* **`ping <IP 또는 Domain>`:**
  * 특정 호스트(예: `ping 8.8.8.8` - Google Public DNS)와의 **네트워크 연결성(Reachability) 및 응답 시간(RTT)을 테스트**.

### 6.2 ICMP (Internet Control Message Protocol)의 역할
* **개념:** IP 프로토콜의 신뢰성을 보완하기 위해 네트워크 통신 상태 및 에러 메시지를 전달하는 계층(L3) 프로토콜.
* **작동 원리:** `ping` 명령어 실행 시, ICMP **Echo Request(요청)** 메시지를 보내고 상대방이 ICMP **Echo Reply(응답)** 메시지를 보냄으로써 통신 여부를 확인.
* **"요청 시간이 만료되었습니다 (Request Timed Out)" 메시지의 의미:**
  * ICMP Echo Request를 보냈으나 일정 시간 내에 Echo Reply를 받지 못함.
  * 원인: 목적지 장비의 전원 OFF, 중간 경로의 방화벽(Firewall)에서 ICMP 트래픽 차단, 네트워크 라우팅 오류 등.
