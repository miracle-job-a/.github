## Hi there 👋

## Project : Job-a
개발자를 위한 취업 플랫폼 - OPEN API를 활용한 MSA 프로젝트


## 서비스 소개
- 개발자가 원하는 조건에 해당하는 공고를 찾을 수 있는 서비스입니다.
- 종료된 공고도 유저에게 계속 보이도록 하여, 원하는 기업 또는 원하는 취업 직종에서 어떤 스택을 요구하는지 미리 파악하고 준비할 수 있도록 하였습니다.
- 능력에 따른 블라인드 테스트가 가능하도록 하였습니다.
- 작은 기업도 쉽게 코딩테스트를 통해 인재를 채용할 수 있도록 하였습니다.
- 공고에 지원한 이력서, 자기소개서, 면접 내용을 공고 별로 한 번에 관리할 수 있도록 하였습니다.


## 팀원 구성
- [전총명](https://github.com/Kade-Jeon) / 스크럼마스터
- 강동희
- 김민지
- 김준영
- 박기철
- 박정민

## 개발 환경
- OS : Mac, Windows
- IDE : IntelliJ
- Front-end : HTML, JavaScript, CSS, Thymeleaf
- Back-end : Java 11, Springboot 2.7.17, 
- DB : Mysql 8.0.33
- Collaboration : ERD cloud, Figma, Github, Github project, Slack, OneDrive
- Server : Tomcat, Nginx
  
## 사용 기술 / API
- AWS EC2 / RDS / S3
- Daum 주소 API
- Firebase API (SSO / 휴대전화 인증)
- Grafana
- Jenkins
- Kakao Map API
- Prometheus
- Spring Data JPA
- Swagger 3.0.0

## CI/CD 파이프라인
<img width="932" alt="image" src="https://github.com/miracle-job-a/.github/assets/58586365/1c782f35-8487-467c-ba4c-03ae262ef062">
- 개발자가 Github에 푸시를 하면 Webhook을 통해 Jenkins에 이벤트 발생을 알립니다.
- Jenkins는 pipeline에 따라 지정된 Github Repository를 Clone 후, 서비스를 Build하여 배포합니다. 이후 배포 결과를 개발자에게 Slack을 통해 성공/실패 여부를 메세지로 알립니다.
- Config-Server를 구현하여 개발환경과 운영환경을 분리하였습니다. 각 설정 파일은 private Repository에서 읽어오도록 하였습니다.
- Eureka-Server를 통해 각 Micro Service들이 서로 찾고 통신할 수 있도록 합니다. 따라서 모든 서비스들은 Eureka-Server에 등록되도록 하였습니다.
- Admin, Company, User Service는 Micro Service로 API를 통해 정보를 반환합니다. 각 서비스들은 RDS와 S3에 접근하여 DB 접근 및 파일 업로드 및 다운로드를 할 수 있도록 하였습니다.
- Util Service는 위 3개 메인 서비스들을 보조하는 부가 기능이 구현된 서비스 입니다.
- 



발표 자료 : https://docs.google.com/presentation/d/1jejjYaOX7zgKc46VwrFa2iFXk3mYz3fmFcPIo4kj1AU/edit?usp=sharing
<!--

**Here are some ideas to get you started:**

🙋‍♀️ A short introduction - what is your organization all about?
🌈 Contribution guidelines - how can the community get involved?
👩‍💻 Useful resources - where can the community find your docs? Is there anything else the community should know?
🍿 Fun facts - what does your team eat for breakfast?
🧙 Remember, you can do mighty things with the power of [Markdown](https://docs.github.com/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
-->
