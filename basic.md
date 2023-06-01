* MVC & MTV
  - Model: 데이터를 저장
  - View: 유저에게 보여줌
  - Control, Template(Django): 사용자의 입력과 이벤트에 반응하여 Model과 View를 업데이트

  ![image](https://github.com/a0lim-python/django/assets/104348646/98460509-f225-4780-b6b0-2aae080533bb)

* Django 개념
![image](https://github.com/a0lim-python/django/assets/104348646/ff0d44d2-1aca-4177-8d63-cbddafc00524)
  - web Browser: 유저가 사용하면서 이벤트 발생
  - URL Dispatcher: url 검사
  - View
  - Model
  - Database
  - template: 유저 인터페이스를 만들어서 web Browser로 보냄

![image](https://github.com/a0lim-python/django/assets/104348646/26b14e75-0f3b-4f4e-8fd9-1eba53a8b5f5)
  - BROWSER -> WEB SERVER -> WSGI -> URL RESOLUTION(정규표현식에 맞게 보냄) -> VIEW(데이터 입출력 판단) -> MODEL(변수 지정) (<-> MANAGERS <-> DATABASE) -> VIEW(데이터 출력) -> TEMPLATE(html) -> BROWSER
  
* Project와 App
  - 프로젝트 생성
    ```django-admin startproject [프로젝트명]```
    + 프로젝트 아래에 __init__.py, settings.py, urls.py, wsgi.py 생성됨
  - app 생성
    ```./manage.py startapp [app명]```
    + 프로젝트 내부에 다수의 app 생성
    + admin.py(관리자 페이지)
    + models.py
    + views.py

* settings.py  
  : 프로젝트 환경 설정 파일
  - DEBUG: true(에러 확인 가능), false(배포 시 설정 필요. 사용자에게 debug 내용 노출 X)
  - INSTALLED_APPS: pip으로 설치한 앱 또는 본인이 만든 app을 추가
  - MIDDELWARE_CLASSES: request, response 사이의 주요 기능 레이어(보안 관련)
  - TEMPLATES: django template 관련 설정, 실제 뷰(html, 변수), 파일 위치 등 파악
  - DATABASES: db 엔진의 연결 설정
  - STATIC_URL: 정적 파일의 URL(css, javascript, image, ...)

* manage.py
  - 프로젝트 관리 명령어 모음
  - 주요 명령어
    + startapp: 앱 생성
    + runserver: 서버 실행
    + createsuperuser: 관리자 생성
    + makemigrations app: app의 모델 변경 사항 체크
    + migrate: 변경 사항을 db에 반영
    + shell: shell을 통해 데이터를 확인
    + collectstatic: static 파일을 한 곳에 모음
  - ex) ./manage.py runserver 0.0.0.0:8080 -> 외부에서 접근 가능한 서버 실행
