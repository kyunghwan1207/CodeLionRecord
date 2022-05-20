# [일단만드는]Django(1)

Django는 `웹 프레임워크` == `웹서비스를 쉽게 만들어주는 기계` 

Django 에 집중하기 보단 
**`웹 서비스를 개발하는 단계, 방법`**에 집중할 것이고 그 도구가 되는 것이 Django이다!

# Ch.2 Python for Django

## Step 1.자료형(dictionary)

우리는 `Key`를 통해 `Value`를 얻는다.

탐색의 기준, 키워드 = `Key`

탐색의 기준에 대응되는, 찾고자 하는 값 = `Value`

**※ Key는 중복되면x, 변하면x**

```python
dic = {key1: val1, key2: val2}
print(dic[key1]) # val1
# dic == {key1: val1, key2: val2}
```

### Step 2.예외처리(Exception Handling)

Python의 오류 종류 2가지

**문법 에러(파싱 에러)**와 **예외**

**문법 에러**: 실행 자체에 영향을 주는 치명적인 오류 (ex. index out of rang, invalid syntax)

**예외**: 프로그램 실행자체를 멈추는 오류 (ex. 자료형 안 맞음, division by zero)

```python
# 방법1
try:
   # 일단 시도해 볼 것
   # 오류가 생길 여지가 있는 코드
except 발생 오류 이름: 
   # 발생 오류가 발생했을 경우 실행할 코드

# 방법2
try:
   # 일단 시도해 볼 것
   # 오류가 생길 여지가 있는 코드
except: 
   # 어떠한 오류가 발생하더라도 경우 실행할 코드

# 방법3
try:
   # 일단 시도해 볼 것
   # 오류가 생길 여지가 있는 코드
except: 
   # 어떤 오류가 발생했을 경우 실행할 코드
finally: 
   # 예외가 발생했든 안했든 최종적으로 무조건 실행할 코드

```

⇒ 프로그램을 `멈춤없이` 실행시킬 수 있다!

### Step 3.클래스와 객체 (객체지향프로그래밍)

OOP의 동기 == 세상에 있는 모든 것들을 프로그래밍 하고 싶다!

객체는 `상태`와 `동작`으로 구성되어 있다

상태와 동작은 `변수` 와 `함수`로 프로그래밍 할 수 있다

```python
# 상태 == 변수
weight = 120
age = 20
# 동작 == 함수
def sleepy():
	if 졸리면:
		잔다
def hungry():
	if 배고프면:
		먹는다
```

세상에 있는 모든 대상(ex. 판다)들은 한두개가 아니라 매우많다…!

⇒ 변수와 함수로 나타낸 상태와 동작을 `여러 개` 만들 수 있어야 한다!

⇒ 즉, `상태`와 `동작`(변수와 함수)을 `한번에 여러 개` 정의할 수 있는 방법이 필요!

== 객체 지향 프로그래밍(Object Oriented Programing, OOP)

![](https://velog.velcdn.com/images/kyunghwan1207/post/48640ae4-c5d1-4b52-b3c2-f1e4eb105b3e/image.png)

### Step 4. 모듈, 패키지, 라이브러리

**모듈**: 파이썬으로 정의된 파일

**패키지:** 모듈의 집합, 모듈의 계층단위

![](https://velog.velcdn.com/images/kyunghwan1207/post/df4253a5-4e6c-47e0-9488-a1570654365f/image.png)

Data는 [Save.py](http://Save.py), Get.py, [Delete.py](http://Delete.py) 모듈들을 담고 있는 패키지이다!

app.py에서는 위와 같이 `import 패키지.모듈` 형식으로 모듈을 사용(모듈 내의 변수, 함수)할 수 있다.

**라이브러리:** 쓸 만한 기능들을 미리 모듈/패키지로 만들어 놓은 것 ****(미리 준비된 모듈 및 패키지 뭉치)

파이썬에서 라이브러리의 두 종류

1. Python Standard Library 
    1. 파이썬 설치시 함께 설치되는 내장함수(ex. len(), print(), input())
2. Python Package Index (PyPI: 파이피아이)
    1. 사람들이 업로드한 라이브러리

⇒ 파이썬 라이브러리들을 관리하는 시스템 필요!

`pip`: Python Package Management System

(ex. pip install 패키지이름)

```python
$ pip install somepackage 
$ pip search somepackage # 패키지 검색
$ pip install somepackage==1.0.4
$ pip uninstall somepackage
```

### Step 5. What is Web Service

정보의 그물망에서 정보의 위치 = URL

정보자원으로 접근하고 통신하게 해주는 프로토콜 = HTTP

**HTTP 요청:** 

GET(”갖다줘!”), POST(”이 데이터 처리해줘!”), PUT(), DELETE

HTML

응답으로서의 정보 자원 자체 or 다른 정보 자원과 연결 매개체

Server

미리 URL, HTML을 가지고 있음. 들어오는 요청을 적절하게 처리해서 응답 return

### Web Service

HTML과 URL을 미리 준비해 놓고 사용자 요청에 대한 응답을 보낼 수 있는 프로그램

### Step 6. What is Web Framework

### 프레임워크

웹 서비스를 쉽게 만들어주는 기계

```python
컴퓨터 프로그래밍에서, 
SW프레임워크는 복잡한 문제를 해결하거나 서술하는데 사용되는 기본 개념 *구조*이다.
간단히 *뼈대*, *골조*, 프레임워크라고도 한다.
```

**프레임워크**는

- 정형화 되어있는 웹 개발을 효율적으로 하기 위해(코드 반복없게) 미리 만들어 놓은 웹 개발의 기능단위, 설계 단위의 집합이다.
- 명확한 목적을 달성하기 위해 이미 설계까지 만들어진 구조/뻐대

**라이브러리**는 

도구의 모음 (프레임워크와 다르다!)

## Step 7. MVC, MTV

1. DB와 상호작용하는 부분 (**M**odel)
2. 사용자들 눈에 보이는 부분 (**V**iew)
3. 내부 동작의 논리를 담당하는 부분 (**C**ontroller)

⇒ 이와 같은 설계원칙을 `“디자인 패턴”`이라고 한다. 즉, Django는 MTV 디자인패턴을 따른다.

Model, Template, View 각각, Model, View, Controller 와 매핑된다. (순서 유의!)

![](https://velog.velcdn.com/images/kyunghwan1207/post/e7c93f22-5d8a-4ccc-a214-7a235c31aa37/image.png)

## Step 8. 개발 환경 세팅

1. 가상환경(virtual environment): 독립적인 개발환경

```python
# 가상환경 만들기
python -m venv {가상환경이름}

# 가상환경 실행하기
source {가상환경이름}/Scripts/activate

pip install django

pip freeze

django-admin startproject myproject

```

## Step 9. Django 뜯어보기

## __*init*__.py

이 언더바 형식의 파일은 python에서 약속된 파일이다.

즉, 언더바 형식의 파일이 존재하는 곳이 패키지가 존재하는 곳이라는 것을 알 수 있음.

## [asgi.py](http://asgi.py) (아스기)

## settings.py

## urls.py

각종 url을 등록해주는 파일, url이 들어올 때, 어떻게 처리할 것인지 정의  

## [wsgi.py](http://wsgi.py) (위스기)

## manage.py

1. **서버 켜기**
    1. `python [manage.py](http://manage.py) runserver`
2. **Application만들기** (**settings.py**에 등록 필요!)
    1. `python [manage.py](http://manage.py) startapp {애플리케이션이름}`
3. **DB 초기화 및 변경사항 반영**
    
    ```python
    python manage.py makemigrations
    python manage.py migrate
    ```
    
4. **관리자 계정 만들기**
    
    ```python
    python manage.py createsuperuser
    Username: admin
    Email address: admin@naver.com
    Password: 1234
    y
    ```
    

## setting.py

`BASE_DIR`

root path라고도 부른다.

프로젝트의 기본 dir위치이다.

`SECRETE_KEY`

비밀번호 암호화할때 사용하는 해시키 값을 나타냄

`DEBUG = True`

개발자 모드로 서버를 킬건지(많은 에러정보 보여줌), 배포용으로 킬것인지(단지Not Found) 정할 수 있음.

`INSTALLED_APPS`

사용할 app 명시

`DATABASE`

어떤 DB쓰고, 그 DB는어디에 있는지

`Internationalization`

국제화, 어떤 기준으로 장고서버의 시간을 맞출 것인지, 언어는 어떤것으로 만들것인지

LANGUAGE_CODE = ‘ko-kr’

TIME_ZONE = ‘Asia/Seoul’

`STATIC_URL`

HTML, JS, CSS, 이미지와 같은 웹서비스에서 미리 준비한 정적인 것들이 어디에 위치하는지 명시

## Step 12. Hello World

1. App 생성 후 [settings.py](http://settings.py) 에 등록
2. App안에 templates폴더안에 화면에 보여질 html페이지 작성
3. [views.py](http://views.py)에서 요청에 따른 응답으로 해당 html페이지를 rendering한다.
4. urls.py를 통해 URL요청에 따라 적절한 [views.py](http://views.py) 안에 함수를 실행시키는 코드추가

```python

# myapp/views.py
from django.shortcuts import render

def home(request):
    # 요청이 들어오면
    return render(request, 'index.html') # 요청과 함께 index.html을 화면에 뿌려줌

# myapp/urls.py
from django.contrib import admin
from django.urls import path
import myapp.views

urlpatterns = [
	path('admin/', admin.site.urls),
	path('', myapp.views.home, name='hello_world'),
]
```

### 순서 중요

1. URL로 접근 + 요청
2. urls.py안에서 URL에 매칭되는 경로에 views.py파일안에 함수를 호출
3. 함수에서 html을 랜더링한다.

# Ch3. [Project1] 회사 소개 사이트

## URL 매핑

include → 다른 app에 접근할때 모든 url경로를 practice_url/urls.py에서만 처리하기 힘드니까

include를 import해서 다른 앱에 인위적으로 [urls.py](http://urls.py) 를 생성해서 각 url에 따라 실행될 함수를 명시해준다.

```python
# practice_url/urls.py
from ast import increment_lineno
from django.contrib import admin
from django.urls import path, include # include추가
from myapp import views

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', views.first), # views안에 있는 first함수를 실행시킨다.
    path('second/', views.second),
    path('products/', include('product.urls')), # proudects라는 url로 오면 product.urls가 처리해줄 것이다!
    path('boards/', include('board.urls')),
]
```

## Step 6. Static

웹 서비스 내부 데이터

1. Static: 미리 준비된 데이터
2. Media: 업로드 된 데이터

### settings.py에서 static관리

- STATICFILES_DIRS: static 파일들의 경로 작성
- STATIC_URL: static 파일을 제공할url
- STATIC_ROOT: static파일들을 복사하여 모아 놓을 경로 (배포할때만 사용)

**배포 시** 

`python [manage.py](http://manage.py) collectstatic`하면 static 파일들이 한 곳으로 모여서 배포 및 관리가 용이해짐

![](https://velog.velcdn.com/images/kyunghwan1207/post/c34a9a82-0151-4b6b-aad1-2cdf2ca3ae5f/image.png)

위와 같이 최상위 폴더에서 static파일을 관리할 수 있고

해당 static 자원을 사용할 html 페이지에서는 아래와 같이 template언어를 통해서 load해서 사용할 수 있다.

![](https://velog.velcdn.com/images/kyunghwan1207/post/19185426-1a1d-4149-9b22-f4a7542e7479/image.png)

만약 app에 한정해서만 static자원을 사용하고 싶다면? 

staticapp이라는 app안에 static이라는 폴더 생성 후 settings.py를 수정해주면 된다!

```python
# static_ex/settings.py
STATIC_URL = '/static/'
STATICFILES_DIRS = [
	BASE_DIR / 'static',
	os.path.join(BASE_DIR, 'staticapp', 'static'), # staticapp/static에 static파일들의 경로 지정
]
STATIC_ROOT = os.path.join('staticfiles') 
# 배포시 staticfiles에 우리의 static파일들을 모아서 배포할 것이다
```

## Bootstrap

[https://getbootstrap.com/docs/5.2/getting-started/introduction/](https://getbootstrap.com/docs/5.2/getting-started/introduction/)

Bootstrap을 내 프로젝트 코드에 적용시키는 방법

1. Bootstrap 관련 코드를 직접 다운(Download) 받아 설치하기
    
    ```python
    # myproject/static폴더 안에 css, js 폴더에 각각 download받은 것 넣기
    # html페이지
    {% load static %}
    <link rel="stylesheet" type="text/css" href="{% static 'css/bootstrap.min.css' %}">
    <script src="{% static 'js/bootstrap.min.js' %}"></script>
    ```
    
2. CDN 이용하기(css, js코드를 온라인 상으로 접근해서 사용, not download)

```python
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.0-beta1/dist/css/bootstrap.min.css">
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.2.0-beta1/dist/js/bootstrap.bundle.min.js"></script>
```

배포할 때는 1번 방식이 더 좋다!

왜냐하면 네트워크 상에서 에러가 발생할 수 있기 때문이다.

## Template 언어

`href = "{% url ‘about’ %"}` 하면 urls.py에서 name=’about’ 으로 지정한 함수로 이동한다.

navbar의 경우 많은 html페이지에서 반복적으로 사용되는 모습을 볼 수 있다

→ 이를 `template상속`을 통해 해결할 수 있다!

### Template 상속

하나의 html파일에 중복되는 코드들을 몰아놓고

다른 html에서는 기존html과 달라지는 부분만 코딩할 수 있게 만들어준다!

 ```python
 # base.html (여러개의 block 존재할 수 있음)
<>
중복되는 코드들
</>
{% block content %}
{% endblock %}
```

```python
# about.html
{% extends 'base.html' %}
{% block content %}
<>
About 페이지 입니다!
</>
{% endblock %}
```

```
