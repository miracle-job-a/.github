## 프로젝트 : Job-a
- 개발자를 위한 취업 플랫폼 - OPEN API를 활용한 MSA 프로젝트
- 팀 : Miracle
- 기간 : 2023.11.02 ~2023.12.20

[<img src="https://img.shields.io/badge/발표자료-FBBC04?style=flat&logo=googleslides&logoColor=white" height=25px />](https://docs.google.com/presentation/d/1jejjYaOX7zgKc46VwrFa2iFXk3mYz3fmFcPIo4kj1AU/edit?usp=sharing)
[<img src="https://img.shields.io/badge/시연영상(PPT Ver.)-FF0000?style=flat&logo=youtube&logoColor=white" height=25px />](https://youtu.be/paDDNcOIIPI?si=ycswEN_LMdLpfMZt)
[<img src="https://img.shields.io/badge/시연영상(Full Ver.)-FF0000?style=flat&logo=youtube&logoColor=white" height=25px />](https://www.youtube.com/watch?v=gh4Vesk6inA)


## 서비스 소개
- 개발자를 위한 취업 플랫폼 서비스입니다.
- 스택, 직무, 근무지역, 경력을 조건으로 원하는 공고를 검색할 수 있습니다.
- 종료된 공고도 유저에게 계속 보이도록 하여, 원하는 기업 또는 원하는 직종에서 어떤 스택이나 기술을 요구하는지 미리 파악하고 준비할 수 있도록 하였습니다.
- 작은 기업도 코딩테스트 바탕으로 인재를 뽑을 수 있는 블라인드 채용 서비스를 지원합니다.
- 공고에 지원한 이력서, 자기소개서, 면접 내용을 공고 별로 한 번에 관리할 수 있도록 하였습니다.
<!--
## 기존 서비스와 차별점

-->
## 팀원 구성

<table>
  <th width=200><img src="https://github.com/Kade-Jeon/Kade-Jeon/blob/main/%E1%84%8B%E1%85%B5%E1%84%86%E1%85%B5%E1%84%8C%E1%85%B5.png?raw=true"></th>
  <th width=200><img src="https://raw.githubusercontent.com/chocolaggibbiddori/chocolaggibbiddori/main/AI%20%EC%A7%A4.webp"></th>
  <th width=200>3</th>
  <th width=200><img src="https://github.com/kimjunyo/kimjunyo/blob/main/Avatar-Maker%20(2).png"></th>
  <th width=200>5</th>
  <th width=200>6</th>
  <tr>
    <td>
      <ul>
        <a href="https://github.com/Kade-Jeon"><img src="https://img.shields.io/badge/전총명-181717?style=flat&logo=github&logoColor=white" height=25px /></a>
      </ul>
    </td>
    <td>
      <ul>
        <a href="https://github.com/chocolaggibbiddori"><img src="https://img.shields.io/badge/강동희-181717?style=flat&logo=github&logoColor=white" height=25px /></a>
      </ul>
    </td>
    <td>
      <ul>
        <a href="https://github.com/hazzokko"><img src="https://img.shields.io/badge/김민지-181717?style=flat&logo=github&logoColor=white" height=25px /></a>
      </ul>
    </td>
    <td>
      <ul>
        <a href="https://github.com/kimjunyo"><img src="https://img.shields.io/badge/김준영-181717?style=flat&logo=github&logoColor=white" height=25px /></a>
      </ul>
    </td>
        <td>
      <ul>
        <a href="https://github.com/Hamel0"><img src="https://img.shields.io/badge/박기철-181717?style=flat&logo=github&logoColor=white" height=25px /></a>  
      </ul>
    </td>
        <td>
      <ul>
        <a href="https://github.com/wjdals3936"><img src="https://img.shields.io/badge/박정민-181717?style=flat&logo=github&logoColor=white" height=25px /></a>
      </ul>
    </td>
  </tr>
</table>




## 개발 환경
- OS : Mac, Windows
- IDE : IntelliJ
- Front-end : HTML, JavaScript, CSS, Thymeleaf
- Back-end : Java 11, Springboot 2.7.17, 
- DB : Mysql 8.0.33
- Collaboration : ERD cloud, Figma, Github, Github project, Slack, OneDrive

  
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
- Gateway Service는 유저와의 접점이자, 각 서비스들을 호출하여 반환받은 정보를 렌더링하여 유저에게 내보내는 서비스 입니다. 따라서 안전한 통신이 될수 있도록 https를 적용하였습니다.


## 담당 파트

<table>
  <th> </th>
  <th width=220>Admin/Company Team</th>
  <th width=220>Gateway Team</th>
  <th width=220>User Team</th>
  <th width=220>Infra Team</th>
  <tr>
    <td>내용</td>
    <td>
      <ul>
        <li>[리더]전총명</li>
        <li>박정민</li>
      </ul>
    </td>
    <td>
      <ul>
        <li>[리더]김준영</li>
        <li>박기철</li>
      </ul>
    </td>
    <td>
      <ul>
        <li>[리더]강동희</li>
        <li>김민지</li>
      </ul>
    </td>
    <td>
      <ul>
        <li>[리더]전총명</li>
        <li>김준영</li>
      </ul>
    </td>
  </tr>
</table>

> 시연이 가능한 기술/기능은 링크를 통해 영상으로 확인할 수 있습니다.

#### 강동희
- User Team 리더
- [User API 개발](https://github.com/chocolaggibbiddori/miracle-job-a-user-service)
- [팀 내 기술 교육 담당 (Java, Spring Framework, Git)](https://chocolaggibbiddori.github.io)
- [DB / Entity 설계](https://www.erdcloud.com/d/YggNYyuaENxFEr27R)
- [Swagger 적용 및 공유](https://www.youtube.com/embed/gh4Vesk6inA?autoplay=1&controls=0&start=836&end=940)
- [JWT 토큰 적용](https://www.youtube.com/embed/paDDNcOIIPI?autoplay=1&controls=0&start=83&end=96)
- [JWT 서버 구축](https://github.com/chocolaggibbiddori/miracle-job-a-util-service)
- [JWT 기반 인증 필터 개발](https://github.com/chocolaggibbiddori/miracle-job-a-gateway-service)
- [API 공통 Response Model 설계](https://github.com/chocolaggibbiddori/miracle-job-a-user-service)

#### 김민지
- User API 개발
- <a href="https://www.youtube.com/embed/gh4Vesk6inA?autoplay=1&controls=0&start=737&end=763">Google Chart 적용</a>

#### 김준영
- Gateway Team 리더
- Gateway Service 개발
- ServiceCall Model 설계
- AWS S3 적용
- <a href="https://www.youtube.com/embed/gh4Vesk6inA?autoplay=1&controls=0&start=35&end=48">이메일 인증 적용 (SMTP)</a>
  
#### 박기철
- Gateway Service 개발
- Front-end 담당
- <a href="https://www.youtube.com/embed/gh4Vesk6inA?autoplay=1&controls=0&start=78&end=103">Daum 주소 API 적용</a>

#### 박정민
- Admin/Company API 개발
- <a href="https://www.youtube.com/embed/gh4Vesk6inA?autoplay=1&controls=0&start=737&end=763">Google Chart 적용</a>


#### 전총명
- Project Scrum master
- Admin/Company Team 리더
- Infra Team 리더
- Admin/Company API 개발
- AWS EC2 / RDS 적용
- <a href="https://www.youtube.com/embed/gh4Vesk6inA?autoplay=1&controls=0&start=949&end=999">Config Server 구축</a>
- <a href="https://www.youtube.com/embed/gh4Vesk6inA?autoplay=1&controls=0&start=941&end=948">Eureka Server 구축</a>
- Jenkins CI/CD 구축
- Slack 알림 적용 (<a href="https://www.youtube.com/embed/gh4Vesk6inA?autoplay=1&controls=0&start=1000&end=1019">배포 알림</a> / <a href="https://www.youtube.com/embed/paDDNcOIIPI?autoplay=1&controls=0&start=29&end=57">코딩테스트 10분 전 알림</a>)
- <a href="https://www.youtube.com/embed/gh4Vesk6inA?autoplay=1&controls=0&start=686&end=717">Prometheus</a> / <a href="https://www.youtube.com/embed/gh4Vesk6inA?autoplay=1&controls=0&start=722&end=737">Grafana </a> 적용
- <a href="https://www.youtube.com/embed/gh4Vesk6inA?autoplay=1&controls=0&start=1037&end=1057">암호화 적용 및 공유 (AES/SHA-3)</a>
- <a href="https://www.youtube.com/embed/gh4Vesk6inA?autoplay=1&controls=0&start=365&end=386">Google Login SSO 적용 (Firebase API)</a>
- <a href="https://www.youtube.com/embed/paDDNcOIIPI?autoplay=1&controls=0&start=13&end=25">휴대전화 인증 적용 (Firebase API)</a>
- <a href="https://www.youtube.com/embed/gh4Vesk6inA?autoplay=1&controls=0&start=16&end=24">Kakao Map API 적용</a>
- Https 적용 (SSL 인증서)
- 도메인 적용

## 협업 방식 - 애자일(Agile)

경험이 부족한 상황에서 워터폴(Waterfall) 방식은 위험성이 크다고 판단하였습니다.
최대한 설계에 공을 들이되, 우리가 부족했던 부분을 언제든 수정하고 반영할 수 있도록 변화에 적극적인 애자일 방식으로 협업을 진행하기로 하였습니다.

협업에 앞서 스크럼(Scrum) 내 그라운드 룰(Ground rule)을 정하여 협업이 더욱 공고히 진행되도록 하였습니다.
스프린트(Sprint)는 기본적으로 1주일 단위로 진행하였고, 프로젝트 후반부에는 2~3일 간격으로 짧게 스프린트를 진행하여 수정사항과 오류에 적극적으로 대응할 수 있도록 하였습니다.
스프린트가 끝나고 스프린트 회고를 통해 백로그(Backlog), 스토리포인트(Storypoint) 등 우리 스크럼에 맞게 조정하여 다음 스프린트에 피드백이 반영될 수 있도록 하였습니다.

업무의 시작과 끝에 데일리체크인 / 체크아웃 (Daily Check-In / Check-Out)을 통해 각 개인의 개발현황, 브로커 등을 공유하도록 하였습니다.
이를 바탕으로 칸반보드를 활용하여 누가 어떤 업무를 진행하고 있는지 시각적으로 보기 쉽게 공유할 수 있도록 하였습니다.

각 스프린트가 끝나면 회고를 통해 피드백이 다음 스프린트 플래닝에 반영될 수 있도록 하였습니다.

[🔍자세히 보기](https://github.com/orgs/miracle-job-a/projects/3)


## 협업 툴 활용

웹 환경에서 6명 모두가 협업할 수 있도록 많은 툴을 최대한 활용했습니다.

ERD Cloud를 이용해 엔티티 설계를 하였고 클라우드 환경에서 언제든 매핑 구조를 한 눈에 파악할 수 있었습니다.
이후, Figma를 이용하여 화면을 스케치하며 초기 기획에서 빠진 기능이나 화면을 추가하였습니다.
프로젝트가 시작되면서 Github을 이용하였고, Github Project를 이용해서 **Agile하게 협업을 진행**하였습니다.
이후 Google Slides를 이용하여 최종 발표자료를 만들었습니다.

🔍 아래 항목을 클릭하면 우리가 협업한 기록을 자세히 볼 수 있습니다.
- [ERD Cloud](https://www.erdcloud.com/d/NZKKeMscHHbw7Xpdf)
- [Figma](https://www.figma.com/file/Qep8MMphIvGhBKXV0KlaRO/Job-a-for-Sharing?type=design&mode=design&t=PbEBNxXV4uaYYYD9-1)
- [Github](https://github.com/orgs/miracle-job-a/repositories)
- [Github Project](https://github.com/orgs/miracle-job-a/projects/3)
- [Google Slides](https://docs.google.com/presentation/d/1jejjYaOX7zgKc46VwrFa2iFXk3mYz3fmFcPIo4kj1AU/edit?usp=sharing)

<!--

**Here are some ideas to get you started:**

🙋‍♀️ A short introduction - what is your organization all about?
🌈 Contribution guidelines - how can the community get involved?
👩‍💻 Useful resources - where can the community find your docs? Is there anything else the community should know?
🍿 Fun facts - what does your team eat for breakfast?
🧙 Remember, you can do mighty things with the power of [Markdown](https://docs.github.com/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
-->
