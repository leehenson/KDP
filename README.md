# KDP

## 1. 서버 구축

내부 고정 IP = 192.168.150.222</br>
test 계정 = ID: test / PW: test</br>
root 계정 = ID: root / PW: root</br>

### 1-1. 서버 PC에 CentOS 듀얼 부팅하기
1. [CentOS 홈페이지](https://www.centos.org/download/)에서 CentOS 7 설치 파일 다운로드 및 [rufus](https://rufus.ie/ko/)로 부팅 가능한 USB로 굽기
2. [BIOS 설정에서 USB 부팅으로 설정](https://blog.naver.com/PostView.naver?blogId=hong0303&logNo=221713594756) 후, 여유 디스크 공간에 CentOS 7 설치
    - [CentOS 7 설치 중 Black Screen 오류 해결법](https://sound10000w.tistory.com/220)

출처
- [여기에 적어놓자](https://boring-notes.tistory.com/entry/Windows-Linux-%EB%A9%80%ED%8B%B0%EB%B6%80%ED%8C%85)
- [C언어 예술가](https://thrillfighter.tistory.com/618)

### 1-2. 랜카드 인식이 안될 때
1. [CentOs7 network 드라이버 설치 과정](https://velog.io/@new_ego_doc/Centos7-network-%EB%93%9C%EB%9D%BC%EC%9D%B4%EB%B2%84-%EC%84%A4%EC%B9%98-%EA%B3%BC%EC%A0%95)을 참고하여 해결

### 1-3. SSH 허용
1. [CentOS 7에서 SSH접속 허용하기](https://kim-yj-0308.tistory.com/3) 참고하여 접속 허용
    - 192.168.150.222:22

### 1-4. SFTP 설정
1. [[CentOS 7] SSH/SFTP 설정](https://testtube.tistory.com/26#google_vignette) 참고하여 SFTP 설정

### 1-5. NVIDIA 그래픽카드 드라이버 설치
1. [Cent OS 7.x Linux Nvidia 그래픽 드라이버 설치 가이드 - \[Linux\]](https://yoon1seok.tistory.com/48) 참고하여 해결
    - ```systemctl isolate multi-user.target``` 입력 후 화면이 안 보일 경우, 다른 컴퓨터로 ssh 접속하여 다음 진행

### 1-6. CentOS7 python-3.10 이상 설치 방법
1. [CentOS 7 Python 3.10 이상 설치](https://velog.io/@och5351/CentOS-7-Python-3.10-%EC%9D%B4%EC%83%81-%EC%84%A4%EC%B9%98) 참조

### 1-7. git 최신버전 설치
1. [CentOS 7 git 최신버전 설치하기](https://dololgun.github.io/linux/centos7-git-install/)

## 2. Stable Diffusion Webui 설치

### 2-1. Stable Diffusion Webui 설치
1. [Stable Diffusion Webui](https://github.com/AUTOMATIC1111/stable-diffusion-webui) 참고하여 linux 버전으로 설치

## 3. CentOS7에서 전자정부표준프레임워크 설치 및 실행
1. [조황섭 유튜브](https://www.youtube.com/watch?v=dfOh9KyUNtU&list=PLrvy0-mRwW-_H8r4W5AgebC-_LEjcIyNF)
2. [프롬달 유튜브](https://www.youtube.com/watch?v=UTpzGuLUXHs&list=PLUOe9aHybotPzBoU4keKsyBGf2S7IbPiT)
    - [JDK 1.8 설치](https://www.youtube.com/watch?v=gCaw4r8XZ3g&t=580s)
    - [eGovFrame 3.10.0 설치](https://www.youtube.com/watch?v=_nmBazcCoxs)
    - [mariaDB 10.5 설치](https://www.youtube.com/watch?v=6FfLBf_7JFY)
    - [공통 컴포넌트와 MaridDB 10.0 연동](https://www.youtube.com/watch?v=6FfLBf_7JFY)
    - [톰캣 9.0 설치 + 공통컴포넌트 실행](https://www.youtube.com/watch?v=MGgtiUaoHsk)

~~### 3-1. All-in-one 컴포넌트 실행 시, DB로 인한 404 에러가 발생할 때~~
~~프로젝트 -> src/main/resources -> egovframework -> egovProps -> globals.properties 파일 열기~~

~~```~~
~~#mysql~~
~~Globals.mysql.DriverClassName=net.sf.log4jdbc.DriverSpy~~
~~Globals.mysql.Url=jdbc:log4jdbc:mysql://127.0.0.1:3306/com~~
~~Globals.mysql.UserName =com~~
~~Globals.mysql.Password =xz4fmrSdr1vGGl6UtwPLwA%3D%3D~~
~~```~~

~~위의 부분을 Data Source Explorer에서 연결한 동일한 DB로 변경해주어야 함.~~