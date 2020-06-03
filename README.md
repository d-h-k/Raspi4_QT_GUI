# Raspi4_QT_GUI
  - 학습목표 : 이번강의에서는 Raspi4 PyQt4에서 
# 1. 이론강의
- 라즈베리파이 OS 설치방법 : 먼저 OS부터 Clean-install 부터 시작!
  - (추천)라즈비안 설치
    - 구글드라이브 링크에서 OS이미지를 다운받아 설치
      - [이미지 다운로드 링크 클릭!](https://drive.google.com/file/d/1r9MPasOY0LY0I5ysVBpq5TQ9AkNVXyyJ/view?usp=sharing)
    - balena-etcher 프로그램 사용해서 SD Card에 burn!
      - https://www.balena.io/etcher/
    - 성공적으로 작업이 완료되면 SD를 라즈베리파이에 장착하고 전원/주변기기들을 장착하고 Booting!
  - 라즈베리파이 OS 설치 (!!사용금지!)
    - (사용금지!) 업데이트된지 5일된 새로나온 OS, 호환성 보장X 
      - https://www.raspberrypi.org/downloads/
    - Raspberry Pi Imager for Windows <<- 링크 클릭!
    - Raspi4 8기가 버전 출시
      - https://www.youtube.com/watch?v=erC2Pu_Jw7o
    - 라즈베리파이 OS는 32비트, 최대 램은 4기가 까지 가능하지만, 문제 해결된 버전
    - 공식홈페이지 링크
      - https://www.raspberrypi.org/products/raspberry-pi-4-model-b/
  - 개발환경 구축 (라즈베리파이)
    ```
    sudo apt-get install update
    sudo apt-get install qtcreator qt5-default
    ```
  - 개발환경구축 HostPC
    ```
    pip install pyqt5
    pip install pyqt5-tools
    ```
  - 설치시 선택사항(OpenCV)
    ```
    pip install python-opencv
    ```
  - 참고링크
    - https://bigwavek.tistory.com/entry/python-PyQt5-%EB%B0%8F-%EC%8B%A4%ED%96%89%ED%8C%8C%EC%9D%BC-%EB%A7%8C%EB%93%A4%EA%B8%B0
  - 설치
    - Windosw Host PC : 아나콘다 설치

- 목차
  ```
  GUI
  1일차 : 
    PyQT 위젯
    시그널과 슬롯
  2일차 : 
    다이얼로그 다루기
    메인 윈도우 만들기
  3일차 : 
    QTableWidget
    데이터 파싱 및 그래프 출력
  4일차 :
    AWS와 DB 연동
    DB 데이터 관리 프로젝트 
  ```
# 2. 이것이 Cross-flatform GUI 의 장점이다!
  ## PC버전 PyQT5 진행 :  
   > https://github.com/d-h-k/Raspi4_QT_GUI/blob/master/PyQT5_PC.md
  ## 라즈베리파이4 PyQT5 : 
   > https://github.com/d-h-k/Raspi4_QT_GUI/blob/master/PyQT5_Rpi4.md
 ## 3) 
 - 스토리 : 큐티는 크로스플랫폼 GUI 프레임웍이라서 리눅스, 윈도우(심지어 맥도!) 돌아간다.
 - 그래서 PC에서 간단하고 빠르고 편하게 파이큐티를 배워보고
 - 라즈베리파이 4에서도 소스코드 옮겨서 (SMABA 사용) 또 돌려본다.
 - 미니프로젝트1 : 라즈베리파이에서 GUI 기능 테스트 프레임워크 제작 
   - 버튼1을 누르면 LED가 켜짐
   - 물리적 스위치를 누르면 GUI상의 스위치에 불이 들어옴
 - 미니프로젝트2 : 
 ## 4) 참조한 링크 밎 자료들 정리
   - 참고 링크 : https://forum.qt.io/topic/105817/qt-creator-on-raspberry-pi4-4gb-ram/3

# 메모
- 이거 왜적어놓은거지
  ```

  1. QtTableWidget
  2. SQLlight로 Query
  3. Matplot Library (그래프)


  1. Thread 예제
  2. OpenCV
  3. GPIO 컨트롤
  4. MySQL Query
  ```

# # Day1 Fisrt
  - 수업자료
  ```
  라즈베리파이 OS 설치방법 : 먼저 OS부터 Clean-install 부터 시작!

    (추천)라즈비안 설치
    구글드라이브 링크에서 OS이미지를 다운받아 설치
    이미지 다운로드 링크 클릭!
    balena-etcher 프로그램 사용해서 SD Card에 burn!
    https://www.balena.io/etcher/
    성공적으로 작업이 완료되면 SD를 라즈베리파이에 장착하고 전원/주변기기들을 장착하고 Booting!
    라즈베리파이 OS 설치 (!!사용금지!)
    (사용금지!) 업데이트된지 5일된 새로나온 OS, 호환성 보장X
    https://www.raspberrypi.org/downloads/
    Raspberry Pi Imager for Windows <<- 링크 클릭!
    Raspi4 8기가 버전 출시
    https://www.youtube.com/watch?v=erC2Pu_Jw7o
    라즈베리파이 OS는 32비트, 최대 램은 4기가 까지 가능하지만, 문제 해결된 버전
    공식홈페이지 링크
    https://www.raspberrypi.org/products/raspberry-pi-4-model-b/
  ```
  
    - 라즈베리파이 PyQt5 설치
      - sudo apt-get install python3-pyqt5
      - sudo apt-get install qttools5-dev-tools

    - 라즈베리파이에 PyQt5가 설치되어있는지 확인
      - python3
      - import PyQt5  

    - 라즈베리파이 OpenCV
      - sudo pip3 install opencv-contrib-python
      - sudo pip3 install opencv-python

    - 라즈베리파이 한글
      - sudo apt-get -y install ibus
      - sudo apt-get -y install ibus-hangul
      - sudo apt-get -y install fonts-unfonts-core


    - 기존 라즈비안 oS 다운로드 링크
      - https://drive.google.com/file/d/1r9MPasOY0LY0I5ysVBpq5TQ9AkNVXyyJ/view  

    - 수많은 PyQt 설치법들..
      - 아나콘다+파이참
        - 가상Python 환경(activate base) : 장점 ->> 여러가지 환경을 꾸며놓고 한PC에서 동시다발적인 프로젝트 진행이 가능하다. 
        - 단점 : 속도가 느려지고..... 배포가 불편하다.. 초보들에게 장애물로 작용한다..
      - pip설치, apt-get 설치(only ubuntu)
        - 저희가 진행한 것, 장점은 : Python을 설치할 수 있는 환경이라면(라즈베리파이, 비글본 블랙... ) 동일하게 설치가 가능하다
        - 단점으로는, 나중에 다른 개발환경을 구축하고자 할때, Ptqt버전이 3.XX 필수로 요구되는경우, 
          - ROS -> APP 파이큐티 3.XXX 을이용해서 제작.
        - 문제가 생기면 python 통째로 삭제 후 재설치
        - autoremove 명령어 활용 (라즈베리파이, 리눅스 기준)
        

- GPIO 파이썬 
  - https://gpiozero.readthedocs.io/en/stable/        
  - https://www.raspberrypi.org/documentation/usage/gpio/python/README.md