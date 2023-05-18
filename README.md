# music 어플 만들기 위한 개발 설정 
## 1. homebrew 설치
  > brew 설치<br>
  > ``` /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"  ``` <br>  
  >  PATH 설정<br>
  >  ``` echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> /Users/snowdeer/.zprofile ```
  >  <br>  ``` eval "$(/opt/homebrew/bin/brew shellenv)" ```
  ## 2. node 설치
  > ```brew install nvm```
  ### 2-1.  nvm setting
  > ```vim ~/.zshenv``` <br>
  > ```export NVM_DIR="$HOME/.nvm"```<br>
  > ```[ -s "/opt/homebrew/opt/nvm/nvm.sh" ] && \. "/opt/homebrew/opt/nvm/nvm.sh"  # This loads nvm```<br>
  > ```[ -s "/opt/homebrew/opt/nvm/etc/bash_completion.d/nvm" ] && \. "/opt/homebrew/opt/nvm/etc/bash_completion.d/nvm"```
<br>

### 2-2 nvm 버전확인
> ``` nvm -v```<br>
> ``` nvm install -version ```<br>

### 2-3 vue 설치 

### 2-4 project 생성 (vue가 설치 되어 있어야지 ionic 사용 가능)
> ``` vue create project(프로젝트명) ```<br>
> ```  npm run serve (test) ```
<br>

#### 설치가 완료 되었으면 xcode_emulator 테스트 필요
 - ionic build 필요<br>
 > ```npm install -g @ionic/cli``` <br>
 > ```ionic start (프로젝트명)``` 
<br>

### 실행 ionic serve <br>
> ```ionic capacitor add ios ``` <br>
>```ionic capacitor open ios```
 <br>
 
## 내용 업데이트 시 
> ```ionic capacitor copy ios``` <br>
> ```ionic capacitor update```

<br>

## IOS에 테스트 하기 위해서 cocoapods설치 필요 
> ```brew install cocoapods```
<br>

# django 설치 
1. homebrew ( 1. homebrew 설치 후 진행 )<br>
   1-1 가상환경 설치 <br>
   > ``` brew install pyenv``` <br>
   > ``` echo 'eval "$(pyenv init -)"' >> ~/.bash_profile ``` <br>
   > ``` pyenv install 3.10.0 (python version) ```<br>
   1-2  virtualenv 설치
   > ``` homebrew install virtualenv ```<br>
   >``` pip install django ``` <br>
   > ``` pip3 install django```<br>

   - project 생성 <br>
   > ``` django-admin startproject crew_server ```<br>
   - 개발할 APP 생성
   >  ``` python3 manage.py startapp (프로젝트명) ``` <br>

   - 실행 <br>
   - 가상환경 on <br>
   > ``` pyenv activate music_server ``` <br>
   > ``` python3 manage.py runserve ``` <br>
   > ``` pip3 install djangorestframework ``` <br>
   - django rest API front 단이랑 연결을 위한 프레임워크 <br>
   > ``` pip3 install django-cors-headers```<br>


## mongodb 설치
### django에서 mongodb 사용을 위한 mongodb 설치 
 - mongodb compas
>``` brew tap mongodb/brew ``` <br>
> ```brew install mongodb-community@5.0 ``` <br>
 - momgo db 시작 
> ``` brew services start mongodb-community@5.0 ``` <br>
 - mongo db 중지  
> ``` brew services stop mongodb-community@5.0 ``` <br>

 - Background Process로 MongoDB 실행 및 중지(M1 프로세스)

> ``` mongod --config /opt/homebrew/etc/mongod.conf --fork ```

 -  Background Process로 MongoDB 실행 및 중지(인텔맥) 
 > ``` mongod --config /usr/local/etc/mongod.conf --fork ```

 - djaong -> mongodb 연결 프레임워크 설치 
 > ``` pip3 install djongo ``` 

# 3. server (django) <br>
-  model 생성 후 makemigrate 필요
 > ``` python3 manage.py makemigrate ``` <br>
 - makemigrate 실행 후 magration 실행
 > ``` python3 python3 manage.py makemigrations CrewBackend ``` 


