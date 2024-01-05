## 프로젝트 : Job-a
개발자를 위한 취업 플랫폼 - OPEN API를 활용한 MSA 프로젝트


## 서비스 소개
- 개발자를 위한 취업 플랫폼 서비스입니다.
- 스택, 직무, 근무지역, 경력을 조건으로 원하는 공고를 검색할 수 있습니다.
- 종료된 공고도 유저에게 계속 보이도록 하여, 원하는 기업 또는 원하는 직종에서 어떤 스택이나 기술을 요구하는지 미리 파악하고 준비할 수 있도록 하였습니다.
- 작은 기업도 쉽게 코딩테스트 바탕으로 인재를 뽑을 수 있는 블라인드 채용 서비스를 지원합니다.
- 공고에 지원한 이력서, 자기소개서, 면접 내용을 공고 별로 한 번에 관리할 수 있도록 하였습니다.


## 팀원 구성

<table>
  <th width=130> </th>
  <th width=200>1</th>
  <th width=200>2</th>
  <th width=200>3</th>
  <th width=200>4</th>
  <th width=200>5</th>
  <th width=200>6</th>
  <tr>
    <td>
        <img src="https://img.shields.io/badge/Github-181717?style=flat&logo=Github&logoColor=white" />
    </td>
    <td>
      <ul>
          <a href="https://github.com/Kade-Jeon">🔗전총명</a>
      </ul>
    </td>
    <td>
      <ul>
        <a href="https://github.com/chocolaggibbiddori">🔗강동희</a>
      </ul>
    </td>
    <td>
      <ul>
        <a href="https://github.com/hazzokko">🔗김민지</a>
      </ul>
    </td>
    <td>
      <ul>
        <a href="https://github.com/kimjunyo">🔗김준영</a>
      </ul>
    </td>
        <td>
      <ul>
        <a href="https://github.com/Hamel0">🔗박기철</a>        
      </ul>
    </td>
        <td>
      <ul>
        <a href="https://github.com/wjdals3936">🔗박정민</a> 
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


> 강동희
- User Team 리더
- User API 개발
- 팀 내 기술 교육 담당 (Java, Spring Framework, Git)
- DB / Entity 설계
- Swagger 적용
- JWT 서버 구축
- JWT 기반 인증 필터 개발
- API 공통 Response Model 설계

> 김민지
- User API 개발
- Google Chart 적용

> 김준영
- Gateway Team 리더
- Gateway Service 개발
- ServiceCall Model 설계
- AWS S3 적용
- 이메일 인증 적용 (SMTP)
  
> 박기철
- Gateway Service 개발
- Front-end 담당
- Daum 주소 API 적용

> 박정민
- Admin/Company API 개발
- Google Chart 적용


> 전총명
- Project Scrum master
- Admin/Company Team 리더
- Admin/Company API 개발
- AWS EC2 / RDS 적용
- Config Server 구축
- Eureka Server 구축
- Jenkins CI/CD 구축
- Slack 알림 적용 (배포 알림 / 코딩테스트 10분 전 알림)
- Grafana 적용
- Prometheus 적용
- 암호화 적용 (AES/SHA-3)
- Google Login SSO 적용 (Firebase API)
- 휴대전화 인증 적용 (Firebase API)
- Kakao Map API 적용
- Https 적용 (Gateway on EC2)

## 협업 방식

🔍 아래 항목을 클릭하면 우리가 협업한 기록을 자세히 볼 수 있습니다. 
- [Figma](https://www.figma.com/file/Qep8MMphIvGhBKXV0KlaRO/Job-a-for-Sharing?type=design&mode=design&t=PbEBNxXV4uaYYYD9-1)
- [ERD Cloud](https://www.erdcloud.com/d/NZKKeMscHHbw7Xpdf)
- [Github](https://github.com/orgs/miracle-job-a/repositories)
- [Github Project](https://github.com/orgs/miracle-job-a/projects/3)
- [발표자료](https://docs.google.com/presentation/d/1jejjYaOX7zgKc46VwrFa2iFXk3mYz3fmFcPIo4kj1AU/edit?usp=sharing)

<!--

**Here are some ideas to get you started:**

🙋‍♀️ A short introduction - what is your organization all about?
🌈 Contribution guidelines - how can the community get involved?
👩‍💻 Useful resources - where can the community find your docs? Is there anything else the community should know?
🍿 Fun facts - what does your team eat for breakfast?
🧙 Remember, you can do mighty things with the power of [Markdown](https://docs.github.com/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
-->
