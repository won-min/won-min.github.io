---
title: "Virus Total"
date: 2026-10-12 02:48:22 +0900
categories: [보안]
tags: [virustotal, soc, malware-analysis]
media_subpath: /assets/img/posts/virustotal/
---

## 요약

- Virus Total이란 여러 개의 백신 엔진과 분석 도구로 파일·URL·도메인·IP를 분석하고, 그 결과를 집계하여 보여주는 서비스이다
- Virus Total은 File·URL·Search 기능을 제공한다
- Virus Total은 악성코드 분석의 초기 분석 단계에서 기초 정보를 모으고 정적·동적 분석의 방향을 잡을 때 사용한다.

---

## Virus Total이란

**virus total이란 여러 개의 백신 엔진과 분석도구로 파일,url,도메인,ip를 분석해서 결과를 집계하여 보여주는 서비스**이다.

실무적으로는 **의심파일을 분석**할 때, **ip·url의 현재 악성 여부와 과거 이력 확인**하는데 사용된다.

공식문서에 따르면 아래와 같은 특징을 가지고 있다.

1\) 무료와 중립성:

- 비상업적 용도로 최종 사용자에게 무료로 제공
- 제3자 엔진을 배포하거나 홍보 X.

2\) 많은 기여자

- VirusTotal의 집계 데이터는 다양한 백신 엔진, 웹사이트 스캐너, 파일 및 URL 분석 도구, 그리고 사용자 기여를 통해 생성

3\) 공유를 통해 글로벌 IT 보안 수준 향상에 기여

- VirusTotal에서 생성한 검사 보고서는 커뮤니티와 공유, 유해 여부 투표 및 댓글을 통해 집단적 이해 심화 및 오탐 여부 식별에 기여

4\) 실시간 업데이트

- 백신 업체에서 배포하는 악성코드 시그니처를 자주 업데이트
- 특정 기여자가 URL을 차단 목록에 추가하는 즉시 사용자에게 표시되는 검사 결과에 반영

5\) 상세 결과

- 특정 백신 솔루션이 제출된 파일을 악성으로 탐지했는지 여부뿐만 아니라 각 엔진의 탐지 레이블(예: I-Worm.Allaple.gen) 등도 표시
- 대부분의 URL 스캐너는 악성 사이트, 피싱 사이트, 의심스러운 사이트 등을 구분

## Virus Total의 기능

바이러스 토탈에 접속하면 아래와 같은 페이지에서 File/Url/Search를 확인할 수 있다.

![VirusTotal 메인 화면](01.png){: w="661" h="378" }
_VirusTotal 메인 화면_

**File**에서는 의심 파일을 여러 백신 엔진으로 동시 검사할 수 있다.

이 탭의 주요 기능은 아래와 같다.

- 다중 엔진 탐지
- 정적 정보 추출 (해시, 형식,PE 구조, 서명)
- 샌드박스 동적 분석
- 연관 파일·도메인·IP 제공

**Url**에서는 의심 링크를 URL 스캐너와 블록리스트로 검사할 수 있다.

이 탭의 주요 기능은 아래와 같다.

- 사이트 유형 판정 (피싱·악성코드 유포 등)
- 리다이렉트·최종 URL
- IP 확인
- HTTP 응답 헤더 제공

**Search**에서는 기존 분석 기록을 조회할 수 있다.

이 탭의 주요 기능은 아래와 같다.

- 해시·URL로 기존 리포트 조회
- 도메인·IP의 맥락 정보 제공(Passive DNS, Whois, 관련 파일)

## Virus Total의 세부적인 사용 방법

**리포트란 분석 대상(파일·URL·도메인·IP)에 대해 VirusTotal이 모은 정보를 정리한 결과 화면**이다.

분석 대상에 따라 File / URL / 도메인·IP 세 종류로 나뉘고, 탭 종류에는 SUMMARY / DETECTION / DETAILS / RELATIONS / BEHAVIOR / CONTENT / SUBMISSIONS / TELEMETRY / COMMUNITY가 있다.

이때, 많은 탭이 무료로 제공되지만 일부 탭은 유료(Enterprise) 고객 전용이다.

### File 리포트

**요약 화면**

의심되는 파일을 업로드하게되면 리포트 화면 상단에서 아래와 같은 요약화면을 볼 수 있다.

![WannaCry 샘플의 File Report 요약 화면](02.png)
_WannaCry 샘플의 File Report 요약 화면_

표시되는 내용은 아래와 같으며, bold 처리한 것은 중요하다고 볼 수 있는 내용들이다.

![출처: VirusTotal 공식 문서](03.png)
_출처: VirusTotal 공식 문서_

1,3. **탐지 비율 - 위협 수준 1차 판단**

2. 커뮤니티 점수

4. SHA-256

5. 파일명

6. **태그 - 파일 형식, 관련 취약점, 실제 행위 등을 확인**

7. **분석 날짜 - 결과가 언제 기준인지 확인**

8. 파일 형식 아이콘

9. **재분석 - 오래된 결과를 최신으로 갱신**

10. 유사 파일 검색 (Enterprise)

11. 샘플 다운로드 (Enterprise)

12. VT Graph

**탭별 항목**

결과 요약 화면 아래에서는 탭 별 상세 내용을 볼 수 있다. 각 탭별 용도 및 표시 내용은 아래와 같다.

1. DETECTION - 위협 유형 또는 위협 여부 파악

![WannaCry 샘플의 DETECTION 탭](04.png)
_WannaCry 샘플의 DETECTION 탭_

- 엔진별 검사 결과 목록
  - 탐지명: 해당 엔진이 악성으로 탐지 (예: Trojan.AndroidOS.Hiddad.C!c)
  - Undetected: 악성으로 탐지하지 않음
  - Suspicious: 의심으로 표시
  - Unable to process file type: 해당 파일 형식을 처리하지 못해 판정 없음
  - Timeout: VirusTotal 실행 시간 제한을 넘어 판정 없음
- 분석 이력 조회(탐지 변화, 이전 분석)와 탐지 결과 복사 (Enterprise)

2. DETAILS - 파일 특성 파악

![WannaCry 샘플의 DETAILS 탭](05.png)
_WannaCry 샘플의 DETAILS 탭_

- 파일 형식별 상세 정보
- 패킹 여부와 패킹 종류
- 파일 생성 일자, 업로드된 파일명 등

3. RELATIONS - 연관 파일·URL로 분석 범위 확장

![WannaCry 샘플의 RELATIONS 탭](06.png)
_WannaCry 샘플의 RELATIONS 탭_

- 파일을 내려받은 URL
- 이 파일을 포함하고 있던 다른 파일
- 실행 파일(PE)의 부모 파일
- 시간에 따른 도메인-IP 매핑

4. BEHAVIOR - 실제 행위 확인

![WannaCry 샘플의 BEHAVIOR 탭](07.png)
_WannaCry 샘플의 BEHAVIOR 탭_

- 제출된 파일을 통제된 환경(샌드박스)에서 자동 실행하고 수행한 행위를 기록
- 파일이 무엇을 하는지 전체적인 개요 제공

5. CONTENT (Enterprise)

- 파일에서 추출한 문자열과 Hex 내용, 형식에 따라 미리보기 제공

6. SUBMISSIONS (Enterprise)

- 제출 이력 상세 (제출 국가, 일자 등)

7. COMMUNITY

- 커뮤니티 회원의 댓글 (최신순)
- 해당 파일·URL에 대한 투표 기록

### URL 리포트

URL을 업로드하여 사이트 유형(피싱, 악성코드 유포 등)을 판정한 결과를 볼 수 있고, 좀 더 세부적인 내용은 아래와 같다.

**요약 화면**

![WannaCry 샘플의 RELATIONS 탭에서 Contacted URL을 다시 조회한 URL Report](08.png)
_WannaCry 샘플의 RELATIONS 탭에서 Contacted URL을 다시 조회한 URL Report_

![출처: VirusTotal 공식 문서](09.png)
_출처: VirusTotal 공식 문서_

1. 탐지 비율

2. URL

3. 소속 도메인

4. 분석 날짜

5. Content type

6. 파비콘

7. 재분석

8. VT Graph

9. Intelligence 검색

10. 커뮤니티 점수

**탭별 항목**

1. DETECTION

- 업체별 판정 결과
  - Clean site: 악성코드 미발견
  - Unrated site: 해당 업체가 평가한 적 없음
  - Malware site: 악성코드 유포
  - Phishing site: 사용자 계정 정보 탈취 시도
  - Malicious site: 익스플로잇 등 악성 요소 포함
  - Suspicious site: 의심 (회색지대)
  - Spam site: 스팸 메일, 팝업, 자동 댓글 등에 연루

2. DETAILS

- 콘텐츠 카테고리, 서버가 반환한 HTTP 응답 헤더 등 추가 정보

3. RELATIONS (Enterprise)

- 파일 리포트와 같은 관계 정보

4. BEHAVIOR (Enterprise)

- URL의 동작과 콘텐츠를 파악하기 위한 종합 분석

5. CONTENT (Enterprise)

- HTML에서 추출한 문자열

6. TELEMETRY (Enterprise)

- URL 텔레메트리 상세 정보

7. COMMUNITY

- 커뮤니티 회원의 댓글 (최신순)
- 해당 파일·URL에 대한 투표 기록

### 도메인·IP 리포트

도메인이나 IP를 업로드하면 아래와 같은 VirusTotal이 관측한 맥락 정보를 볼 수 있다.

**요약 화면 및 제공 정보**

![도메인 Report 요약 화면](10.png)
_도메인 Report 요약 화면_

![IP 주소 Report 요약 화면](11.png)
_IP 주소 Report 요약 화면_

1. AS·국가

2. Passive DNS

3. Whois

4. 하위 도메인

5. 형제 도메인

6. URLs

7. Downloaded files

8. Communicating files

9. Files referring

## Virus Total을 통한 분석 방법

Virus total은 악성코드 분석의 초기 분석(Triage) 내지는 기초분석 단계에서 기초 정보를 모으고 이후 정적·동적 분석의 방향을 잡을때 사용한다.

이때, 주의해야할 사항이 여러가지 있다.

- VT에서 확인한 정보는 참고목적으로만 사용하고, 직접 분석을 통해 구체적 정보를 확인하도록한다. VT의 탐지 결과와 실제 분석 결과가 다를 수 있기 때문이다.
- 내부 문서는 업로드하지 않는다. Virus total은 업로드되는 문서가 공유될 수 있기 때문이다.
- 분석 날짜가 오래되었다면, 재분석을 수행한다. 그 사이 백신 엔진이 업데이트되어 지금 검사하면 탐지 결과가 달라질 수 있기 때문이다.
- 미탐지라고해서 꼭 안전하다는 뜻은 아니다. 신종이나 표적형 악성코드는 모든 엔진에서 탐지되지 않을 수 있기 때문이다.
- VT 결과와 실제 제품의 결과는 다를 수 있다. VirusTotal의 엔진은 명령줄 버전·전용 설정이라 실제 제품의 동작과 다를 수 있기 때문이다.
- 악성 사이트라고 해서 악의적 운영자가 운영하는 것은 아니다. 정상 사이트가 침해된 경우도 많기 때문이다.
