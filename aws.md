# vs코드와 리눅스를 사용하며 AWS 서버에 배포하는 방법

## AWS 서버 생성

![20230526_105104](https://github.com/ijd1236/Amazon/assets/130967884/bd94ab10-5839-4623-b0cb-7183a2df9b16)
![20230526_105119](https://github.com/ijd1236/Amazon/assets/130967884/4ea5b940-67df-4ec1-a925-6ea9615a8322)
![20230526_105140](https://github.com/ijd1236/Amazon/assets/130967884/2a148cef-7b54-49ff-b01c-8f4e48f08a10)
![20230526_105232](https://github.com/ijd1236/Amazon/assets/130967884/0127b7ec-9d1c-4378-826a-22715c60a26d)
![20230526_105304](https://github.com/ijd1236/Amazon/assets/130967884/046c2710-c0b4-4f98-9cef-a1884a1d83f1)

- 이렇게 AWS 서버를 생성 완료합니다.

![20230526_145402](https://github.com/ijd1236/Amazon/assets/130967884/1fa6533d-2fcb-4459-8681-f63512ce816a)

- 서버 생성시 인스턴스에 1개가 실행되고 있다고 나옵니다.

## 리눅스 사용을 위헌 PuTTY 다운로드

![20230526_104741](https://github.com/ijd1236/Amazon/assets/130967884/089f75e5-228e-4ce9-add4-7581c0f50f6e)

![20230526_104826](https://github.com/ijd1236/Amazon/assets/130967884/cf8e165c-3fc6-43d3-a6c8-7bf7326a46df)

![20230526_104852](https://github.com/ijd1236/Amazon/assets/130967884/1c891a6a-7def-4cd1-a7be-e14c1c5851ad)

### 푸티 환경 설정

![0 0](https://github.com/ijd1236/Amazon/assets/130967884/91b9c545-5bae-4288-af8d-194e438631f0)

- AWS 서버에서 퍼블릭 ip 주소 복사
- 
![0 1](https://github.com/ijd1236/Amazon/assets/130967884/143d14f6-3d3a-4410-a016-aee9f2b8c5a4)

![1](https://github.com/ijd1236/Amazon/assets/130967884/ff943f05-8ebd-4237-aa33-48ad41c57d75)

- AWS 서버 만들 때 받았던 키패드를 넣는다
- 
![2](https://github.com/ijd1236/Amazon/assets/130967884/d804a3b4-51f3-47f8-a9cc-b755d70f365f)

- 설정한 내용을 저장 후 Open 으로 실행

### 리눅스의 기본적인 명령어
![0](https://github.com/ijd1236/Amazon/assets/130967884/80ead9f5-8388-41d9-b1a4-6cb29d948ec7)

![1](https://github.com/ijd1236/Amazon/assets/130967884/5826f1df-cd3c-4b1a-89cc-f43121f776de)

- ec-user를 입력해 AWS 서버 들어가기

## 푸티에 아나콘다 설치
![20230525_162538(1)](https://github.com/ijd1236/Amazon/assets/130967884/2d8bdd28-0658-4e9b-b11a-da3be229d857)
![20230525_162538(2)](https://github.com/ijd1236/Amazon/assets/130967884/d3746b0c-14c6-4602-be42-a0aa47db74b8)

- 리눅스용 들어후 링크 주소 복사

![20230525_162644](https://github.com/ijd1236/Amazon/assets/130967884/bb880513-b7c1-4519-98b0-2ae3d7629bd5)

- wget 아마존 파일 링크주소 로 아마존 설치폴더를 다운받는다

![20230525_162712](https://github.com/ijd1236/Amazon/assets/130967884/5dff8915-d97c-4efc-949f-fc7b445e86d2)

- 다운 완료후 아마존이 받아져 있는지 확인

![20230525_163337](https://github.com/ijd1236/Amazon/assets/130967884/e29fb3b3-b8d7-4eff-8d34-3a87a88eaaad)

- 전부 완료하면 아마존이 설치된다


## PuTTY에서 앱 대시보드 만들기

- PuTTY는 SSH의 기능을 수행하는 프로그램

- conda create -n app_dash python=3.9 openssl numpy scipy matplotlib ipython scikit-learn pandas pillow jupyter seaborn 로 가상환경 설정, 라이브러리를 받는다.

![image](https://github.com/ijd1236/Amazon/assets/130967884/5bdf6c86-a4ec-4fb4-a252-d458d064a6ed)

- conda activate app_dash 로 가상환경에 들어간다
- streamlit 설치 : pip install streamlit
- plotly 설치 = pip install plotly ==5.14.1
- joblib 설치 = pip install joblib==1.2.0

### 깃허브에서 소스파일을 가져오기 (Clone)

- 리눅스에 Git 설치 = sudo yum install git
- 만약 yum update 관련 오류가 났을때는, sudo yum update 실행하고 sudo yum upgrade 실행 후 다시 git 설치

#### AWS EC2 에서 보안(방화벽) 항목에서 포트 허용해주기

- 








