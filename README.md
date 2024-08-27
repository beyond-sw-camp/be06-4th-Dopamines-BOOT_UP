<h1 align="center"> 데브옵스 아키텍처 구현 </h1>


<br>

<br>

## 🤼‍♂️팀원 소개 


<div style="display: flex; justify-content: center;">
  <table>
    <tbody>
      <tr>
        <td align="center"><a href="https://github.com/JungDongSeob" style="text-decoration: none; color: lightgray;"><img src="assets/image/sundongguri.jpg" width="100px;" height="100px;" background-size="cover;" alt=""/><br /><sub><b> 🐯 곽동현</b></sub></a><br /></td>
        <td align="center"><a href="https://github.com/kangmoonhye" style="text-decoration: none; color: lightgray;"><img src="https://i.pinimg.com/222x/4e/92/54/4e9254d45725666a3fe8855e9cca5ba9.jpg" width="100px;"  alt=""/><br /><sub><b> 🐶 김동욱</b></sub></a><br /></td>
        <td align="center"><a href="https://github.com/SongYeonBaek" style="text-decoration: none; color: lightgray;"><img src="https://pbs.twimg.com/profile_images/3008255612/a56d6133b8f6aa19afecd19c79536a76_400x400.png" width="100px;" height="100px;" alt=""/><br /><sub><b> 🐱 한별</b></sub></a><br /></td>
        <td align="center"><a href="https://github.com/Hyeon28" style="text-decoration: none; color: lightgray;"><img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRich3DFlHTCbrEzOhs6gt6fnn1PUsNBopG2w&s" width="100px;" alt=""/><br /><sub><b> 🐧 최정완</b></sub></a><br /></td>
            <td align="center"><a href="https://github.com/dohyun0408" style="text-decoration: none; color: lightgray;"><img src="https://pbs.twimg.com/profile_images/3009669833/cae9685e735be56bfe84f5f1a2748e2f_400x400.jpeg" width="100px;" alt=""/><br /><sub><b> 🐺 안준홍</b></sub></a><br /></td>
      </tr>
    </tbody>
  </table>
</div>



## ✨ 프로젝트 기본 소개

- 

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

### Docker, k8s, Jenkins를 활용하여 "Frontend" 와 "Backend" 프로젝트에 CI/CD를 적용한다.

<br>

## CI/CD 의 필요성 ❓

#### 팀원끼리 기능을 만든 후 하루에 여러번 코드변경 및 통합하는 과정이 지속적으로 반복되고
#### 그에 따라 충돌이 자주 발생하거나 코드품질이 하향될 수 있다.
#### ➡ 개발주기 초기에 문제를 감지하고 충돌없이 코드품질이 유지되도록 보장해주면서 
#### 동시에 작업할 수 있도록 해주는 CI의 필요성이 대두되었다.
#### 개발자가 코드 변경에 따른 빌드 및 테스트 과정을 수동으로 해야하고 그에 따른 코드 검증 및 배포에 시간이 많이 소요된다. 
#### ➡ 새로운 기능을 추가하거나, 에러를 수정할 때마다 지속적으로 배포해줄 수 있는 CD의 필요성이 대두되었다.

<br>

## CI/CD 의 기대효과 💥

#### 통합된 코드를 자동으로 빌드하고 테스트할 수 있고, 이를 통해 코드 충돌이나 오류를 빠르게 발견하고 수정이 가능해지며, 
#### 코드를 안정적으로 배포 가능한 상태로 유지하며, 자동으로 실제 운영 환경에 배포가 가능해진다. 
#### 또한 코드의 버그나 이슈가 초기에 발견되 수정비용이 줄어들고, 그에 따라 리스크가 감소된다. 


  <br>

---

## 🖥️ 운영 환경 : 쿠버네티스 & 컨테이너 운영 환경 구성

### 🧐 쿠버네티스를 이용한 이유

### ✅ 유연성
#### 단일 서버에 여러 컨테이너를 배포하거나 여러 서버에 분산하여 컨테이너를 배포할 때 자동으로 관리해주고 
#### 트래픽의 양에 따라서 리소스를 많이 할당하거나 적게 할당해주는 유연성을 가지고 있다.

<br>

### ✅ 일관성 및 자가치유기능

#### 쿠버네티스를 사용하면 개발부터 프로덕션까지 일관된 운영 환경을 유지할 수 있다. 이는 환경 간 불일치로 인한 문제를 줄여주고 
#### 배포 및 운영 과정에서 발생하는 오류를 최소화할 수 있다. 또한 실패한 컨테이너를 자동으로 감지하고 재시작하거나, 
#### 정상적으로 동작하지 않는 노드를 제외하는 등 자가 치유 기능을 제공해 시스템의 안정성을 유지하게 해준다.

<br>

---

### 📁 &nbsp;&nbsp;k8s 클러스터 구성도

<br>

[//]: # (![클러스터 구성도]&#40;./img/clusterArchitecture.jpg&#41;)

#### ✅ k8s 클러스터는 총 5대의 노드로 클러스터를 구성했다.

<details>
  <summary><b>노드 상세 정보(사진)</b></summary> 
  <br>    
  <img src="./img/nodesInfo.png"/>


- #### 쿠버네티스는 클러스터의 네트워크 환경을 효율적으로 관리하고 네트워크 구성 요소와 밀접하게 통합되는 가상 네트워크 드라이버를 설치해줘야하므로 CNI 소프트웨어 중에서 Calico를 선택했다.
    #### Calico는 성능, 보안, 확장성, 유연성 측면에서 뛰어나고 특히 네트워크 정책 관리가 필요한 대규모 컨테이너 클러스터에서 효과적으로 사용되며,
    #### 간단한 배포와 운영, 그리고 클라우드 및 온프레미스 환경 모두에서 잘 작동하는 네트워크 관리 도구라는 점에서 Calico를 선택했다.

- #### Calico는 LoadBalancer Type의 서비스를 제공하지 않으므로, "metallb" 를 추가로 사용하게 되었다.
- #### "metrics" 는 HPA를 통한 Autoscaling 구현 즉, metrics를 기반으로 파드의 수를 자동으로 조절하기 위해 사용했다.

</details>
<br>

<details>
<summary><b>Pod 상세 설명</b></summary>  
<br>

### ✅ 각 Worker 노드에는 다음과 같은 파드가 공통적으로 생성된다.

> - **calico-node : 네트워크 정책을 관리하고 구성하는 역할**
>
> - **metalib-system : 클러스터 내에서 로드 밸런싱 및 외부 서비스 노출을 담당하는 역할**

<br>

### ✅ Master Node에는 다음과 같은 파드들이 추가된다.

> **kube-system Namespace**
>
> - **coredns : 클러스터 내에서 DNS 서버 역할**
> - **calico-kube-controllers : 클러스터 내에서 네트워크 정책을 관리하고 구성하는 역할**
> - **metrics-server : 클러스터 내에서 파드 및 노드의 리소스 사용량 및 성능 지표를 수집하고 노출하는 역할**

<br>

> **metailb-system Namespace**
>
> - **speaker : 외부 라우팅 장치와 통신하여 로드 밸런서에 할당된 IP 주소를 라우팅하는 역할**
> - **controller : 클러스터 내에서 IP 주소 범위를 관리하고, 외부 서비스에 IP 주소를 동적으로 할당하고** > &nbsp;　　　　　**회수하는 역할**

 <br>

---

</>
</details>



## 💡&nbsp;&nbsp;시스템 아키텍처
<br>

<img src="./img/systemArchitecture.jpg">

<br>

- #### 프론트엔드, 백엔드 각각의 디플로이먼트를 통해 파드로 생성된다.
- #### 사용자들은 LB (LoadBalancer) 타입의 Frontend-svc를 통해 웹 포트로 Nginx 서버에 접근하여 서비스를

#### &nbsp;&nbsp;&nbsp;　이용한다.

- #### 파드들 간의 통신은 ClusterIp 타입의 서비스를 통해 내부 통신으로 이루어진다. 따라서 외부에 노출 되지

#### &nbsp;&nbsp;&nbsp;　않는다.

<br>

## 💽&nbsp;&nbsp;CI/CD 시스템 아키텍처

<br>

### 🧐 배포 시 고려사항

<br>

### < 무중단 배포를 해야하는 이유 >

#### 새로운 버전으로 배포 시 실행중인 서버를 종료하고 새로운 버전의 서버빌드를 진행해야하는데 이렇게 중단배포를 하게되면
#### 유저들이 서비스를 이용할 수 없는 다운타임이 발생하게 된다. 따라서 유저들이 서비스 이용에 불편함을 느끼지 않게 하기 위하여
#### 무중단 배포를 선택했다.

---

### < Blue/Green 방식을 사용한 이유 >

#### Blue/Green 방식은 카나리배포보다는 구현 방식이 간단하고, 호환성 문제가 발생하지 않는다는 장점이 있다. 일정 비율을 정해서
#### 부하분산을 해줄 수 있는 카나리배포방식은 일정 비율만큼 부하분산을 해주면서 새로운 버전의 서비스를 테스트하기 용이하나 
#### 우리 서비스에서는 카나리배포방식을 사용할 정도의 규모가 아니라는 판단 하에 복잡한 방법보다는 조금 더 간단하고 빠른 롤백을
#### 할 수 있는 Blue/Green구현 방식을 선택하게 되었다.

---

<br>

#### ( 주의 ❗)

#### Blue/Green 방식으로 무중단 배포를 할 때, 발생할 수 있는 문제는 동일한 운영 환경에서 다른 버전의 인스턴스를 생성하기 때문에 

#### 프로그램이 로딩 되는 사이에는 서비스가 중단되는 상황이 발생한다.

#### 따라서, 컨테이너 내부의 프로그램이 준비가 완료됬을 때, 파드가 삭제되도록 "Health check " 하는 방법으로

#### readiness 및 liveness probe 를 사용했다.

<br>
<img src="./img/cicdArhitecture.jpg">

<br>

### 🚀 배포 시나리오 : Blue/Green 방식을 이용한 무중단 배포

#### 1. develop branch에서 통합이 이루어지면, github action이 Junit을 통해 작성된 테스트 코드를 실행한다.

#### 2. 깃허브(원격 저장소) main branch 에 최신 버전의 프로젝트가 "push" 된다.

#### 3. 깃허브는 젠킨스에게 Webhook을 보낸다.

#### 4. 젠킨스는 파이프라인에 저장된 절차를 실행한다.

#### &nbsp;　 a. 젠킨스 서버에 깃허브의 있는 프로젝트를 가져온다. (git clone)

#### &nbsp;　 b. 프로젝트가 벡엔드라면 "mvn package", 프로젝트가 프론트엔드라면 "npm run build" 를 통해 빌드 한다.

#### &nbsp;　 c. 빌드를 통해 생긴 "jar" 또는 "dist 폴더" 를 이용해 Dockerfile로 Docker image 를 만든다.

#### &nbsp;　 d. Docker image를 Docker hub에 "push" 한다.

#### &nbsp;　 e. 젠킨스 서버에서 k8s master에 "deployment" yaml file을 전송한다.

#### &nbsp;　 f. k8s master에서 yaml file들을 적용시킨다. ( kubectl apply )

[//]: # (#### &nbsp;　 g. 파이프라인을 진행하면서 단계마다 시작, 종료, 결과를 젠킨스 서버에서 Jenkins CI 를 통해)

[//]: # ()
[//]: # (#### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;　 Slack으로 전송한다.)

[//]: # ()
[//]: # (#### &nbsp;　 h. Slack을 통해 개발자들은 파이프라인 진행 현황을 확인할 수 있다.)

#### 5. 최종적으로 Blue/Green 방식을 통해 무중단 배포가 이루어 진다.

<br>

---

<br>

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
         <br>
        <details>
         <summary><b>Backend Slack 알람</b></summary>
                  <br>
         <p>
         <b>➡ 각 단계마다 slack 알람이 온다. </b>
         <br>
         <p><img src="./img/backendSlack.gif"/></p>
         </details>
         <br>
	    <details>
         <summary><b>무중단 배포</b></summary>
         <br>
         <p><b>
         ➡ 클러스터 내부 컨테이너에서 backend-svc로 요청을 보낸다.
         ➡ 요청이 지속적으로 오는 가운데 main 브런치에 push 한다.
         ➡ 에러 메시지가 나오는지 확인한다.
         ➡ 변경 사항이 적용되었는지 확인한다.
         </b></p><br>
         <p><img src="./img/backenddeployment.gif"/></p>
         </details><br>
    </div>
</details>
<br>







---

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