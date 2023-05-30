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
![20230526_172757](https://github.com/ijd1236/Amazon/assets/130967884/ecd343b7-9221-4ade-8158-91107aec4ffd)

#### 작업전 clone할 폴더 생성하기

- mkdir.Github를 입력하여 clone할 Github라는 이름의 폴더를 생성해줍니다

#### 리눅스 Github폴더 내에서 깃허브 닷컴의 HTTPS 를 이용해서 clone 하기

- 먼저 가상환경에서 sudo yum install git 을 입력하여 리눅스내에서 git을 다운 받습니다.

![20230530_153514](https://github.com/ijd1236/Amazon/assets/130967884/36bce0d8-7d8a-433f-896a-3612641b1725)



- git clone '깃허브 레파지토리 https 주소'를 복사후 

![image](https://github.com/ijd1236/Amazon/assets/130967884/48c12806-88f8-4bc6-aa24-e297d164f55e)

- 리눅스 가상환경(Gith 폴더내)에서 'it clone 복사한 주소' 입력합니다

![20230530_153654](https://github.com/ijd1236/Amazon/assets/130967884/e89a7d56-5f40-4103-8704-85eae03ed947)

![20230530_153805](https://github.com/ijd1236/Amazon/assets/130967884/f2013c9f-8b28-47a4-ab11-bd50bc26bfcf)

- clone 완료후'll' 입력하여 설치가 제대로됐는지 확인합니다.

- clone할 레파지토리가 퍼블릭이 아닐 경우 아이디와 패스워드를 입력해야합니다.

- 아이디는 깃허브 아이디를 그대로 입력하면되고
- 패스워드는 토큰을 만들어 입력합니다.
- 
##### 깃허브 토큰 생성방법
![20230526_102418](https://github.com/ijd1236/Amazon/assets/130967884/b2dc063e-0476-4171-9faa-583ce5112482)

![20230526_102449](https://github.com/ijd1236/Amazon/assets/130967884/6b708e2b-412a-4cc1-8cc7-16887fe7b2d1)

![20230526_102502](https://github.com/ijd1236/Amazon/assets/130967884/93c28c65-8999-4d53-9bc1-7f9088fe3e48)

![20230526_102540](https://github.com/ijd1236/Amazon/assets/130967884/01debfe8-3333-4941-b34f-d00fbeeb9a54)


![20230526_102557](https://github.com/ijd1236/Amazon/assets/130967884/63433f07-c194-4421-8b0c-3aaf920355b6)


![20230526_102557](https://github.com/ijd1236/Amazon/assets/130967884/5a7ba79a-fa44-41a0-b369-078032e68e82)



- 이제 깃허브 clone 이 완료되어 PuTTY에서 깃허브 파일을 사용하여 앱 대시보드 실행이 가능해졌습니다.

![image](https://github.com/ijd1236/Amazon/assets/130967884/9413cf9d-f250-41ab-bd3f-742b15359e3e)

- http://3.36.131.111:8502 를 주소창에 입력하면 대시보드에 들어갈 수 있습니다.
- 여기서 3.36.131.111은 퍼블릭 ip 주소에 해당하고 8502는 포트번호에 해당합니다.

### 클론 디렉토리로 이동해서 단순 터미널에서 실행하기
- streamlit run app.py 로 앱대시보드를 실행했을 때
- 터미널을 끄면 앱도 꺼지는 문제점이 존재합니다.
- 터미널을 종료하더라도 계속해서 앱이 유지 되도록 하겠습니다.

- 먼저 백그라운드에서 앱을 실행하려면 먼저 AWS에서 인바운드 규칙을 추가 설정해야합니다
![20230526_103644](https://github.com/ijd1236/Amazon/assets/130967884/88947e59-5ee9-4f56-9db9-cb59a56b4b3d)

![20230526_103845](https://github.com/ijd1236/Amazon/assets/130967884/50448046-c88d-44b9-9bd0-4bff2b6af154)


![20230526_103954](https://github.com/ijd1236/Amazon/assets/130967884/37983d50-c648-4aa9-9839-f974a1d6998e)

- 이제 nohup streamlit run app.py & = nohup(꺼도 서버 지속) streamlit run app.py &(빽그라운드에서 돌아라)
- 를 사용하여 백그라운드에서 앱이 돌아가게 할 수 있습니다.
- 백그라운드에서 돌아가는 앱을 종료하려면  먼저
-  pgrep -f "streamlit run app.py" 나 ps -ef | grep streamlit 를 입력해 id를 확인하후
-  kill 아이디 를 입력해 종료할 수 있습니다.

## vs 코드에서 변경후 배포
- vs코드에서 설정을 변경 후 (제대로 작동되는지 실행해봐야합니다.) 변경 내용을 커밋 & 푸시 한 이후
- 그 이후 PuTTy에서 git pull 를 입력해 깃허브에서 수정한 내용을 반영합니다.
- cat 파일이름.py 로 파일 내용을 확인할 수 있습니다.

## 깃허브를 이용한 Agile(애자일) 개발 방식 사용

- Agile 방식이란 신속한 반복 작업을 통해 실제 작동 가능한 소프트웨어를 개발하여 지속적으로 제공하기 위한 소프트웨어 개발 방식을 말합니다.
-  여기선 깃허브에 변경한 내용을 AWS 서버에 바로 적용할 수 있게 만듭니다.
-  
![20230526_124229](https://github.com/ijd1236/Amazon/assets/130967884/ab64a7a3-1807-425d-beb4-421ea2380d51)


![20230526_124638](https://github.com/ijd1236/Amazon/assets/130967884/17dd7e50-60d4-4f12-ab2d-cdba69009e5f)

- 깃허브에서 작업하는 레파지토리 선택후 세팅 - > 액션즈에 들어갑니다.

![20230526_124741](https://github.com/ijd1236/Amazon/assets/130967884/f832d19b-6d67-4496-831f-cc5b8a497a33)

- 동작할 암호를 설정합니다.
![20230526_124856](https://github.com/ijd1236/Amazon/assets/130967884/51195763-8c47-4a2d-8a4c-666aabf023d3)

- 먼저 이전에 받았던 pem 파일을 연후 그 내용을 입력하고 규칙을 만듭니다.

![20230526_125702](https://github.com/ijd1236/Amazon/assets/130967884/8466540f-c624-4f4d-8cc9-5f4e278a8632)

- 유저의 네임 (서버이름)을 추가합니다.

![20230526_125754](https://github.com/ijd1236/Amazon/assets/130967884/f8c94f97-af33-4763-a4f3-001b1f7f9a97)

- AWS ec2의 ip 주소를 입력하고 추가합니다.
 
![20230526_125840](https://github.com/ijd1236/Amazon/assets/130967884/9b82e9c1-ad3c-48c1-ada3-c61b75e5d8f1)

- 규칙을 만든 후 액션즈에서 workflow 를 설정합니다.

### 세팅 코드

![20230526_131541](https://github.com/ijd1236/Amazon/assets/130967884/9f6c19e9-61cd-4d62-a2f6-cb32525847bc)

- 깃허브 레파지토리가 프라이빗으로 만들어져 있을때. 
- 시크릿을 아이디와 (GIT_USER) 토큰 내용으로(GIT_PASSWORD) 두개 만든다
- git pull https://${{ secrets.GIT_USER }}:${{ secrets.GIT_PASSWORD }}@github.com/ijd1236/car_price_dash_board.git  <- @ 뒤는 깃허브 주소


이것으로 기본적인 AWS 환경 설정이 완료되었습니다.













