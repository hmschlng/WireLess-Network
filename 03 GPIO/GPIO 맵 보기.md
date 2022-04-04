# GPIO
---
<br>

# GPIO란?
라즈베리파이 보드에는 40개의 핀이 있는데, 이 핀을 GPIO라고 합니다.
GPIO는 General Purpose I/O 의 약자로, 직역하여 범용 입출력이라는 의미입니다. GPIO를 사용하여 외부 주변기기와 연결하여 상호작용할 수 있습니다.
<br>

##### Raspberry Pi 4 GPIO
![111](https://i.imgur.com/FQUdMWO.png)
[☝🏼 reference](https://www.etechnophiles.com/raspberry-pi-4-gpio-pinout-specifications-and-schematic/)
<br>

# RaspberryPi 4 핀 맵 (BCM)
GPIO의 핀은 각 핀을 구분하기 위해 이름이 있는데, 그 명칭 셋이 여러가지가 있습니다. 

- Naming Sets
  - Physical
  - BCM
  - wPi

#### Physical (물리적 핀 번호)
핀의 물리적인 구성에 따른 번호 구분법입니다. SD카드 슬롯이 위로 올 때 기준으로, 핀 좌측 상단부터 1번, 그 오른쪽 핀은 2번, 둘째 줄 왼쪽 핀은 3번, ... 순으로 40번 핀까지 있습니다.
<br>

#### BCM 번호
라즈베리파이의 메인 프로세서의 제조사인 Broadcom사에서 정한 핀 번호 명칭체계로, BCM GPIO 핀 번호라고 합니다. 이 핀 번호는 BCM283x의 물리적인 핀 번호를 그대로 적용하고 있으며, Python 기본 라이브러리에서는 이 BCM Naming Set을 사용하고 있습니다.
<br>

#### wPi 번호
wPi (wiringPi) Naming Set은 GPIO 핀의 넘버링을 우선순위로 매칭한 명칭법입니다. 예를 들어 GPIO.2번 포트의 경우 wPi 명칭도 2번입니다.
<br>
 
#### ☝🏼 Naming Set 마다 핀 번호당 위치가 각각 다릅니다. 따라서 공식 라이브러리가 아닌 라이브러리를 사용할 때는 어떤 Naming Set을 사용하여 작성되었는지 반드시 확인해야 합니다.
<br>

##### GPIO Pinout Map ( Physical / BCM / wPi )
![111](https://workshop-iot-programming.devbit.be/assets/img/pinout_wiring_pi.56491fd7.png)
<br>

## 라즈베리파이 터미널로 GPIO 맵 보기
#### 1. wiringpi-latest.deb 패키지를 설치합니다.
#### 2. gpio readall 로 pinout map을 조회합니다.
<br>

```shell
# /tmp 로 이동 (#1)
$ cd /tmp 

# wget으로 wiringpi-latest.deb 파일 다운로드 (#2)
$ wget https://project-downloads.drogon.net/wiringpi-latest.deb

# dpkg(데비안 패키지 설치 프로그램)으로 gpio설치
$ sudo dpkg -i wiringpi-latest.deb 

# 설치한 gpio 프로그램 버전 확인
$ gpio -v 

# gpio 핀 맵 조회
$ gpio readall
```
<br>

## 수행 결과
![gpio_pinmap](https://i.imgur.com/b4Oxi8W.png)
<br>

---
##### #1) '/tmp' 에 대한 정보 : https://m.blog.naver.com/hongjg3229/221814662731

##### #2) wget에 대한 정보 : https://jokerkwu.tistory.com/43