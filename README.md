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
    - 프로젝트 폴더생성 -> 해당폴더로 이동 cd 경로명
    - 폴더내에서 가상환경 만들기 : python -m venv myvenv
    - 가상환경 이용 : 
      - 들어가기 myvenv\Scripts\activate
      - 나가기 deactivate
    - 장고패키지 설치: 
      - python -m pip install --upgrade pip
      - pip install django~=2.0.0

3. 몰랐던 부분
    - 폼 사용
    - 로그인 사용자



