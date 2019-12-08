# my_first_blog
장고걸스 튜토리얼 그대로 따라하기
- 강의: https://tutorial.djangogirls.org/ko/
- 구현: https://dowtech.pythonanywhere.com/
- 윈도우 기준, 아나콘다 설치, Visual Studio Code 사용
- cmd 또는 Anaconda prompt를 관리자권한으로 실행

1. python 설치하기 또는 아나콘다를 설치함
    - 버젼 확인 : python --version 
    - window : 다운받은뒤 설치
    - linux : sudo apt install python3.6 (OS에 따라 명령어 다름)

2. 가상환경 및 장고설치
    - 왜 가상환경을 설정해야하는가?
        - 개발 환경을 깔끔하게 관리하는 데 큰 도움이 되는 도구
        - Virtualenv는 프로젝트 기초 전부를 Python/Django와 분리해줍니다. 
        - 다시 말해 웹사이트가 변경되어도 개발 중인 것에 영향을 미치지 않는다는 것.
    - 프로젝트 폴더생성 -> 해당폴더로 이동 cd 경로명
    - 폴더내에서 가상환경 만들기 : python -m venv myvenv
    - 가상환경 이용 : 
      - 들어가기 myvenv\Scripts\activate
      - 나가기 deactivate
    - 장고패키지 설치: 
      - python -m pip install --upgrade pip
      - pip install django~=2.0.0 # 2.0대로 설치 (버전설정 없을시 최신버전)
      - pip install "django<2" # 2.0 미만으로 설치
      - django-admin --version # 장고설치 확인
      - pip freeze > requirements.txt # 설치패키지 리스트 생성

3. 장고 사용하기 대략적인 순서
    ```
    (1) django-admin startproject 프로젝트이름 . #점은 현재폴더에 생성
    (2) manage.py가 있는 폴더로 이동
    (3) python manage.py startapp 앱이름
    (4) settings.py 수정
        (a) app등록, timezone수정
        (b) templates, static 위치추가 , 폴더생성(app하위 또는 최상위)
    (5) python manage.py migrate # 기본테이블 생성
    (6) python manage.py createsuperuser # 관리자 생성
    (7) python manage.py runserver # 사이트 확인    
    (8) model.py 수정
    (9) admin.py 에 모델등록 # admin사이트에서 볼수있도록
    (10) python manage.py makemigrations
    (11) python manage.py migrate
    (12) model 작성 -> url conf 매핑 -> view함수 -> template
    (13) view 함수형 기본예시
        - def 함수이름(request) context={} return render(request, 'html', context)
        - def 함수이름(request) context={} return redirect(reverse('polls:result')) 
        - def 함수이름(request) context={} return HttpResponseRedirect(reverse('polls:result')) 
    (14) template -> 기본html -> base.html 만든다음 template 상속
    
    ```

4. Git 사용하기
    - Git 설치, 프로젝트 폴더에서 Git Bash 실행
    - Github 가입 및 저장소(repository) 만들기, readme 체크X, 나중에 만들기 
    - 저장소 주소 복사
    - gitignore 작성하여 특정파일 업로드 무시할수있음.
    - PC에서 Github 저장소로 처음 올리기
        ``` 
        (a) git init
        (생략) echo "아무내용" > README.md
        (생략) echo "아무내용" > .gitignore
        (b) git config --global user.name "이름"
        (c) git config --global user.email "이메일"
        (d) git add .
        (e) git commit -m "first commit"
        (f) git remote add origin 깃헙주소
        (g) git push -u orgin master
        강제로 업로드 git push -u origin +master
        ```
    - PC에서 Github으로 업데이트
        ``` 
        (d) git add --all . 또는 git add .
        (e) git commit -m "second commit"
        (g) git push 또는 git push -u orgin master
        ```    
    - Github에서 PC로 처음 가져오기
        ``` 
        - git clone 깃헙주소
        ```        
    - Github에서 PC로 가져오기(패치)
        ``` 
        - git pull
        ```            
    - PC에서 Github으로 업데이트 (패치 후 올리기)
        ``` 
        - git fetch
        - git diff origin/master
        - esc -> !q
        - git pull
        - https://stackoverflow.com/questions/19085807/please-enter-a-commit-message-to-explain-why-this-merge-is-necessary-especially
            (1) Press "i"
            (2) Enter you message after "#"
            (3) Press "esc"
            (4) at the very bottom write ":wq"
            (5) Press "Enter"
        - git add .
        - git commit -m "third commit"
        - git push
        ```           

5. 몰랐던 부분
    - 폼 사용
    - 로그인 사용자



