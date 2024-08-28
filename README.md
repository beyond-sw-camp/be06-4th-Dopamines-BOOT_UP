<h1 align="center"> 데브옵스 아키텍처 구현 </h1>


<br>

<br>

## 🤼‍♂️팀원 소개 


<div style="display: flex; justify-content: center;">
  <table>
    <tbody>
      <tr>
        <td align="center"><a href="https://github.com/706com" style="text-decoration: none; color: lightgray;"><img src="assets/image/sundongguri.jpg" width="100px;" height="100px;" background-size="cover;" alt=""/><br /><sub><b> 🐯 곽동현</b></sub></a><br /></td>
        <td align="center"><a href="https://github.com/postrel63" style="text-decoration: none; color: lightgray;"><img src="https://i.pinimg.com/222x/4e/92/54/4e9254d45725666a3fe8855e9cca5ba9.jpg" width="100px;"  alt=""/><br /><sub><b> 🐶 김동욱</b></sub></a><br /></td>
        <td align="center"><a href="https://github.com/shinebyul" style="text-decoration: none; color: lightgray;"><img src="https://pbs.twimg.com/profile_images/3008255612/a56d6133b8f6aa19afecd19c79536a76_400x400.png" width="100px;" height="100px;" alt=""/><br /><sub><b> 🐱 한별</b></sub></a><br /></td>
        <td align="center"><a href="https://github.com/choijw1116" style="text-decoration: none; color: lightgray;"><img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRich3DFlHTCbrEzOhs6gt6fnn1PUsNBopG2w&s" width="100px;" alt=""/><br /><sub><b> 🐧 최정완</b></sub></a><br /></td>
            <td align="center"><a href="https://github.com/wergx" style="text-decoration: none; color: lightgray;"><img src="https://pbs.twimg.com/profile_images/3009669833/cae9685e735be56bfe84f5f1a2748e2f_400x400.jpeg" width="100px;" alt=""/><br /><sub><b> 🐺 안준홍</b></sub></a><br /></td>
      </tr>
    </tbody>
  </table>
</div>


<!--
## ✨ 프로젝트 기본 소개
- 
-->
<br>

## 📌 기술 스택

&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://img.shields.io/badge/GitHub-181717?style=flat&logo=GitHub&logoColor=white&color=black"></a></a>
&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://img.shields.io/badge/Git-F05032?style=flat&logo=Git&logoColor=white&color=ffa500"></a></a>
&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://img.shields.io/badge/GitHub Actions-2088FF?style=flat&logo=GitHub Actions&logoColor=white&color=gray"></a></a>
&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://img.shields.io/badge/Jenkins-D24939?style=flat&logo=jenkins&logoColor=white"/></a></a>
&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://img.shields.io/badge/Docker-2496ED?style=flat&logo=Docker&logoColor=black&color=blue"/></a></a>
&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://img.shields.io/badge/Kubernetes-326CE5?style=flat&logo=Kubernetes&logoColor=blue&color=skyblue"/></a></a>
<!--
&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://img.shields.io/badge/Slack-4A154B?style=flat&logo=Slack&logoColor=yellow&color=purple"/></a></a>
-->
<br>
<br>

---

## 🤳 프로젝트 목표

### Docker, k8s, Jenkins를 활용하여 "Frontend" 와 "Backend" 프로젝트에 CI/CD로 구성해 개발단계로 들어가려한다.

<br>

---



## 💡&nbsp;&nbsp;시스템 아키텍처
<br>

[//]: # (<img src="./img/systemArchitecture.jpg">)

<br>




### 구성요소
- #### 프론트엔드 deployment
- #### 백엔드 deployment
- #### 젠킨스
- #### 도커 
- #### 도커허브
- #### 노드5개
- #### 유저
- #### 깃헙                                                                                                                                                                                                 

<br>

#### 유저가 깃헙에 변경사항을 푸쉬하면 Webhook을 통해서 젠킨스 파이프라인에서 파이프라인 실행
#### project 빌드후, jar파일로 도커빌드를 하고 도커허브에 push 해준다.
#### push해준 후에 쿠버네티스에서 프론트 또는 백 프로젝트를 배포한다.


<br>

## 💽&nbsp;&nbsp;CI/CD 배포 방식 및 시나리오

<br>



### 🧐 Blue/Green 방식을 사용한 이유 

#### 새로운 버전으로 배포 할때 유저들이 서비스를 이용할 수 없는 다운타임이 발생하게 된다. 
#### 이 떄 유저들이 서비스 이용에 불편함을 느끼지않도록 블루그린 무중단 배포를 선택했다. 현재 우리 서비스는 개발초기단계이므로 유저유입과 데이터 축적이 먼저라고 판단했다. 따라서 버전별로 일정부하를 주면서 새버전에 대해서 유저의 반응과 호응도를 분석하기에 적합한 카나리방식보다는 블루그린방식이 더 적합하다고 판단했다.

### 🧐 추후 개선방향
#### 추후 서비스에 충분한 유저가 유입되고, 어느정도 데이터가 축적된 후에는 점진적으로 트래픽을 분산시켜 유저의 반응을 볼 수 있는 카나리 배포를 적용시킬 예정이다. 유저 반응을 쉽게 볼 수 있는 프론트는 카나리 배포를 적용시켜, 새로운 버전에 대한 반응을 파악하고 에러가 발생하면 빠르게 반응할 수 있도록 개선할 생각이다.






<br>
<!--
#### ( 주의 ❗)
#### Blue/Green 방식으로 무중단 배포를 할 때, 만약 서버가 구동중인 상황이 클라우드나 가상환경이 아니라면? 정말 그냥 컴퓨터를 통해 물리적인 서버로 존재한다면? 
#### 기존에 있던 서버의 환경과 같은 수준의 서버를 두배로 늘렸다가 필요 없어지면 다시 줄이는 비 효율적인 방식을 선택할 수 없다. 한마디로, 물리적으로 존재하는 서버에서는 사용하기 어려우며 현재위치 배포 방식이 더 어울린다. Blue/Green방식은 쉽게 인스턴스를 생성하고 없앨 수 있는 클라우드 환경이나, 컨테이너를 올렸다가 내리는 것이 자유로운 Docker등의 가상환경에서 사용하는 것이 바람직하다.
-->
<br>
<img src="./img/cicdArhitecture.jpg">

<br>

### 🚀 배포 시나리오 : Blue/Green 방식을 이용한 무중단 배포

#### 1. 프로젝트 업데이트 및 변경사항을 git에 push한다.

#### 2. 깃허브(원격 저장소) main branch 에 최신 버전의 프로젝트가 "push" 된다.

#### 3. 깃허브는 젠킨스와 연동된 Webhook을 통해 변경된 프로젝트를(변경사항을)? 보낸다.

#### 4. 젠킨스는 파이프라인에 저장된 절차를 실행한다.

#### &nbsp;　 a. 젠킨스 서버에 깃허브의 있는 프로젝트를 가져온다. (git clone)

#### &nbsp;　 b. 프로젝트가 벡엔드라면 "sh ./gradlew bootjar", 프로젝트가 프론트엔드라면 "npm run build" 를 통해 빌드 한다.

#### &nbsp;　 c. 빌드를 통해 생긴 "jar파일" 또는 "dist 폴더" 를 이용해 Dockerfile로 Docker image 를 만든다.

#### &nbsp;　 d. Docker image를 Docker hub에 "push" 한다.

#### &nbsp;　 e. 젠킨스 서버에서 k8s master에 "deployment" yaml file을 전송한다.

#### &nbsp;　 f. k8s master에서 yaml file들을 적용시킨다. ( kubectl apply )

[//]: # (#### &nbsp;　 g. 파이프라인을 진행하면서 단계마다 시작, 종료, 결과를 젠킨스 서버에서 Jenkins CI 를 통해)

[//]: # ()
[//]: # (#### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;　 Slack으로 전송한다.)

[//]: # ()
[//]: # (#### &nbsp;　 h. Slack을 통해 개발자들은 파이프라인 진행 현황을 확인할 수 있다.)

#### &nbsp;   g. 변경된 버전과 라벨에 따라서 신버전(green)의 deployment를 연결해준다.

#### &nbsp;   h. 구버전의 deployment의 파드수를 0으로 변경 후 연결을 끊어준다.

#### 5. 최종적으로 Blue/Green 방식을 통해 무중단 배포가 이루어 진다.

<br>

---


## 💻 CI/CD 시연 영상

<br>
<details>
<summary><b>🤵🏻‍♂️ Backend CI/CD </b></summary><br>
    <div>
    <details>
         <summary><b>Jenkins Pipeline</b></summary>
                  <br>
         <p><b>
          ➡ 백엔드 응답 메시지를 바꾸고 깃에 푸시
          ➡ 파이프라인이 작동
          ➡ 파드가 새로 생성
          ➡ 바뀐 응답메시지 확인
          </b></p><br>
         <p><img src="./img/backendPipeline.gif"/></p>
         </details>
    </div>
</details>
<br>


<br>






<!--

## ✨ 프로젝트 기본 소개

<br>

### 프로젝트 배경
- 배경적기

### 프로젝트 목표
- 목표적기


<br>

---

## 📌 시연사이트 바로가기

### 📊 시연사이트링크넣기

<br>

---

## 📌 기술 스택

<br>

### 🚀 Frontend
<div align="left">
<img src="https://img.shields.io/badge/html5-E34F26?style=for-the-badge&logo=html5&logoColor=white" style="border-radius: 5px;"/>
<img src="https://img.shields.io/badge/css3-1572B6?style=for-the-badge&logo=css3&logoColor=white" style="border-radius: 5px;"/>
<img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=JavaScript&logoColor=white" style="border-radius: 5px;"/>
<img src="https://img.shields.io/badge/Vue.js-4FC08D?style=for-the-badge&logo=Vue.js&logoColor=white" style="border-radius: 5px;"/>
<img src="https://img.shields.io/badge/vue_router-4FC08D?style=for-the-badge&logo=Vue.js&logoColor=white" style="border-radius: 5px;"/>
<br>

[//]: # (<img src="https://img.shields.io/badge/VCALENDAR-4FC08D?style=for-the-badge&logo=Vue.js&logoColor=white"/>)
<img src="https://img.shields.io/badge/jwt-000000?style=for-the-badge&logo=Json Web Tokens&logoColor=purple" style="border-radius: 5px;">
<img src="https://img.shields.io/badge/pinia-gold?style=for-the-badge&logo=Pinia&logoColor=white" style="border-radius: 5px;"/>
<img src="https://img.shields.io/badge/axios-5A29E4?style=for-the-badge&logo=Axios&logoColor=white" style="border-radius: 5px;"/>
<img src="https://img.shields.io/badge/nginx-009639?style=for-the-badge&logo=nginx&logoColor=white" style="border-radius: 5px;"/>
<img src="https://img.shields.io/badge/eslint-4B32C3?style=for-the-badge&logo=eslint&logoColor=white" style="border-radius: 5px;"/> 
</div>

### 🚀 Backend
<div>
<img src="https://img.shields.io/badge/spring-%236DB33F.svg?style=for-the-badge&logo=spring&logoColor=white" style="border-radius: 5px;">
<img src="https://img.shields.io/badge/Spring Boot-6DB33F?style=for-the-badge&logo=Spring Boot&logoColor=white" style="border-radius: 5px;">
<img src="https://img.shields.io/badge/Spring_Security-6DB33F?style=for-the-badge&logo=Spring-Security&logoColor=white" style="border-radius: 5px;">
<img src="https://img.shields.io/badge/Spring data jpa-6DB33F?style=for-the-badge&logo=Spring Boot&logoColor=white" style="border-radius: 5px;">
<img src="https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white" style="border-radius: 5px;"> 
<br>

<img src="https://img.shields.io/badge/IntelliJ_IDEA-000000.svg?style=for-the-badge&logo=intellij-idea&logoColor=white" style="border-radius: 5px;"> 

[//]: # (<img src="https://img.shields.io/badge/kafka-231F20?style=for-the-badge&logo=apachekafka&logoColor=white"> )
<img src="https://img.shields.io/badge/jwt-000000?style=for-the-badge&logo=Json Web Tokens&logoColor=purple" style="border-radius: 5px;">
</div>

### 🚀 &nbsp;DB
<div>
<img src="https://img.shields.io/badge/MariaDB-003545?style=for-the-badge&logo=mariadb&logoColor=white" style="border-radius: 5px;"> 
</div>

### 🚀 &nbsp;CI/CD
<div >
<img src="https://img.shields.io/badge/k8s-326CE5?style=for-the-badge&logo=#326CE5&logoColor=white" style="border-radius: 5px;">
<img src="https://img.shields.io/badge/docker-2496ED?style=for-the-badge&logo=docker&logoColor=white" style="border-radius: 5px;">
<img src="https://img.shields.io/badge/jenkins-D24939?style=for-the-badge&logo=jenkins&logoColor=white" style="border-radius: 5px;">
<img src="https://img.shields.io/badge/git-F05032?style=for-the-badge&logo=git&logoColor=white" style="border-radius: 5px;">
<img src="https://img.shields.io/badge/github-181717?style=for-the-badge&logo=github&logoColor=white" style="border-radius: 5px;">

<br>

[//]: # (<img src="https://img.shields.io/badge/grafana-F46800?style=for-the-badge&logo=grafana&logoColor=white" style="border-radius: 5px;">)

[//]: # (<img src="https://img.shields.io/badge/prometheus-E6522C?style=for-the-badge&logo=prometheus&logoColor=white" style="border-radius: 5px;">)

[//]: # (<img src="https://img.shields.io/badge/slack-4A154B?style=for-the-badge&logo=slack&logoColor=white" style="border-radius: 5px;">)
<img src="https://img.shields.io/badge/webhook-2088FF?style=for-the-badge&logo=webhook&logoColor=white" style="border-radius: 5px;">
</div>


### 🚀 TEST Tools
<div>

[//]: # (<img src="https://img.shields.io/badge/Jest-323330?style=for-the-badge&logo=Jest&logoColor=white" style="border-radius: 5px;"> )

[//]: # (<img src="https://img.shields.io/badge/JUnit-123456?style=for-the-badge&logo=Junit&logoColor=white" style="border-radius: 5px;">)

[//]: # (<img src="https://img.shields.io/badge/selenium-43B02A?style=for-the-badge&logo=selenium&logoColor=white" style="border-radius: 5px;">)
</div>

<br>

---



## &nbsp;&nbsp;📌 프로젝트 설계

<br>

### &nbsp;&nbsp; &nbsp;[ 피그마(Figma) 바로가기](https://www.figma.com/file/xj93UowlHUunCPSqImxspk/LAT32T?type=design&node-id=0-1&mode=design&t=itaxJcadJzP1pjEG-0)

<br>

### &nbsp;&nbsp; &nbsp;[ 요구사항정의서 바로가기](https://docs.google.com/spreadsheets/d/121T1XodlKwX98hXcoRJmiMPKQaZVn3RyZAUTDPQm5UY/edit?usp=sharing)

<br>

<!-- 
### &nbsp;&nbsp; &nbsp;[ API 명세서 바로가기](https://www.notion.so/0d57403fe28943c3997598c0de35ceb9?v=f54966510f6c4223b61c64146d9c1940&pvs=4)
<br>



### &nbsp;&nbsp; &nbsp;[ ERD 및 시스템 아키텍쳐 바로가기](https://docs.google.com/spreadsheets/d/121T1XodlKwX98hXcoRJmiMPKQaZVn3RyZAUTDPQm5UY/edit?usp=sharing)
[//]: # (    <img src="img/ERD_latest.png"/>)
[//]: # (<img src="backend/img/system_architecture.png"/>)

<br>
-->

<!--

## &nbsp;📌 프로젝트 설명


### 👉&nbsp;&nbsp; Front
- LoadBalacer type의 서비스에 의해 외부에 연결되어 있다.
- nginx의 Reverse Proxy를 통해 front주소 /api가 붙어 있으면 k8s안의 Backend Service에 연결한다.
- 채팅 및 알람 기능은 연결을 지속적으로 유지하기 위해 http1.1이상 규격을 사용해야하며 nginx가 Reverse proxy 적용시 http1.1을 유지 하게 한다.
- 채팅의 경우 header가 http에서 ws로 upgrade 할 수 있도록 설정한다.
- Deployment로 k8s에서 작동하며 부하분산을 위해 2개의 pod로 운영된다.
- RollingUpdate 방식으로 무중단 배포 된다.

#### 🤔 [ Frontend 설명 더보기 ](https://github.com/beyond-sw-camp/be06-4th-SYNerge/wiki/Frontend)
<br>

### 👉&nbsp;&nbsp;Back
- SCDF에 의해 batch서버가 1분에 한번씩 pod로 작동하며, 이때 회원의 일정을 조회를 해서 메세지를 produce 하여 Cluster Ip를 통해 kafka broker로 전달한다. kafka broker는 Backend 서버에게 메세지를 전달하며, Backend는 메세지를 consume 하여 Frontend에게 SseEmitter를 통해 데이터를 전송한다.
- Deployment로 k8s에서 작동하며 부하분산을 위해 2개의 pod로 운영된다.
- 2개의 서버의 websocket session이 서로 달라 채팅 데이터가 누락이 될 수 있어, 채팅 메세지가 생성되면 kafka broker에게 전달하고 그 메세지를 2개의 서버가 consume한다.
- RollingUpdate 방식으로 무중단 배포 된다.
- Front, DB, kafka와 cluster ip로 통신하여 외부에 노출되지 않는다.

#### 🤔 [ Backend 설명 더보기 ](https://github.com/beyond-sw-camp/be06-4th-SYNerge/wiki/Backend)
<br>

### 👉&nbsp;&nbsp;CI/CD
- 개발자 Github에 push하게 되면, webhook에 의해 Jenkins가 작동한다.
- Jenkins는 pipeLine script에 따라 git clone, build, docker image build, docker image push의 과정을 거쳐 manifest 파일을 k8s master 서버 전송 후 deployment를 실행한다.

#### 🤔 [ CICD 설명 더보기 ](https://github.com/beyond-sw-camp/be06-4th-SYNerge/wiki/CI---CD)


-->