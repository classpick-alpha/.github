<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=14&height=200&section=header&text=ClassPick&fontSize=72&fontColor=ffffff&fontAlignY=40&desc=교내%20강의실%20대여%20플랫폼&descAlignY=62&descSize=20&descColor=c8d8ff&animation=fadeIn" />

<br/>

&nbsp;
<a href="https://youtu.be/VfbLoOTYFNQ"><img src="https://img.shields.io/badge/시연 영상-FF0000?style=for-the-badge&logo=youtube&logoColor=white" /></a>

<br/><br/>


<br/>


</div>

<br/>


## 배경 및 목적

교내 강의실 대여 절차는 **오프라인 서류 기반**으로 최소 3~5일이 소요되며, 학생 80% 이상이 절차 자체를 모를 만큼 접근성이 낮은 상태였습니다. ClassPick은 이 문제를 해결하기 위해 학생과 교직원이 함께 사용할 수 있는 온라인 실시간 예약 플랫폼을 구축했습니다.


| | 기존 방식 | ClassPick |
|:---|:---|:---|
| 대여 소요 시간 | 최소 3 ~ 5일 | 즉시 신청 |
| 신청 방법 | 오프라인 서류 방문 제출 | 온라인 클릭 몇 번 |
| 운영 시간 | 09:30 ~ 16:00 제한 | 24시간 |
| 상태 확인 | 실시간 확인 불가 | 실시간 현황 제공 |
| 노쇼 방지 | 수기 관리 | OCR 자동 검증 |

<br/>



## 주요 기능

**학생**
- 구글 계정 로그인 (국민대 계정 전용)
- 건물 · 참석 인원 · 날짜 · 시간 필터링으로 빈 강의실 탐색
- 타임테이블 드래그로 원하는 시간 선택 후 예약 신청
- 마이페이지에서 예약 상태 칸반 / 테이블 뷰로 관리

**교직원**
- 엑셀 파일 업로드로 강의실 일괄 등록
- 학생 예약 요청 목록 조회 후 승인 / 반려
- 강의실별 노쇼 비율 차트 시각화

**노쇼 방지 시스템**
- 사용 후 강의실 사진 업로드 (S3 Presigned URL)
- PaddleOCR로 이미지에서 강의실 호수 자동 추출
- 예약 정보와 대조 후 이용 완료 처리

<br/>



## 유저 플로우

<div align="center">
<img src="./docs/classpick_userflow.png" width="780"/>
</div>

<br/>



## 시스템 아키텍처

<div align="center">
<img src="./docs/classpick_architecture.png" width="780"/>
</div>

<br/>

- Seoul Region 내 **Multi-AZ** 구성으로 고가용성 확보
- Elastic Load Balancing 으로 트래픽 분산, Auto Scaling Group 으로 탄력적 확장
- Private Subnet 에 **RDS(MySQL) + ElastiCache(Redis)** 격리 배치
- Amazon S3 로 노쇼 인증 이미지 저장 및 Presigned URL 발급
- 국민대학교 Authorization Server 와 연동한 **Google OAuth 2.0** 인증

<br/>



## 기술 스택

<div align="left">

| 분류 | 기술 |
|:---|:---|
| Frontend | Next.js · React · TypeScript · TailwindCSS · Zustand · Zod · Axios |
| Backend | Spring Boot · Java 21 · Spring Security · JWT · JPA |
| Database | MySQL (AWS RDS) · Redis (ElastiCache) · Amazon S3 |
| Infra | AWS EC2 · ALB · Auto Scaling · Docker · GitHub Actions |
| Monitoring | Sentry · Prometheus · Grafana |
| 협업 | Jira · Figma · Postman · GitHub |

</div>

<br/>



## 팀원

<div align="left">

| 이름 | 역할 |
|:---:|:---:|
| 탁태현 | PM | 
| 윤성욱 | Backend | 
| 김민재 | Backend | 
| 손대현 | Frontend | 
| 이어진 | Frontend | 
| 서명균 | UI/UX Design | 

</div>

<br/>



## 발표 자료

<img src="./docs/classpick_slide-01.jpg" width="780"/>
<img src="./docs/classpick_slide-02.jpg" width="780"/>
<img src="./docs/classpick_slide-03.jpg" width="780"/>
<img src="./docs/classpick_slide-04.jpg" width="780"/>
<img src="./docs/classpick_slide-05.jpg" width="780"/>
<img src="./docs/classpick_slide-06.jpg" width="780"/>
<img src="./docs/classpick_slide-07.jpg" width="780"/>
<img src="./docs/classpick_slide-08.jpg" width="780"/>
<img src="./docs/classpick_slide-09.jpg" width="780"/>
<img src="./docs/classpick_slide-10.jpg" width="780"/>
<img src="./docs/classpick_slide-11.jpg" width="780"/>
<img src="./docs/classpick_slide-12.jpg" width="780"/>
<img src="./docs/classpick_slide-13.jpg" width="780"/>
<img src="./docs/classpick_slide-14.jpg" width="780"/>
<img src="./docs/classpick_slide-15.jpg" width="780"/>
<img src="./docs/classpick_slide-16.jpg" width="780"/>
<img src="./docs/classpick_slide-17.jpg" width="780"/>

<br/>



<div align="center">

더 나은 캠퍼스 공간 경험을 만듭니다

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=14&height=120&section=footer" />

</div>
