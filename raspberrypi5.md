## 라즈베리파이 5 설치, 그리고 느낀점

2023년 12월, 라즈베리파이 5는 내 책상의 first com이 되었다.
라즈베리파이 3/4가 가끔씩 사용하는 용도였다면, 라즈베리파이 5는 데스크탑 역할을 충분히 해준다.

그래서 라즈베리파이 5의 설치 및 설정 내용을 기록해둔다.

1. 한글 설정  
  리눅스 설치의 시작은 항상 한글 설정이다.  
   . 한글 글꼴과 입력기 설치 방법  
    ```
    sudo apt-get install fonts-nanum fonts-nanum-coding fonts-naver-d2coding
    sudo apt-get install ibus ibus-hangul
    ```
   . 한글 입력기 추가  
    `IBus 설정 > Input Method > Add > Korean-Hangul`

2. 시스템 업데이트
    ```
    sudo apt-get update
    sudo apt-get upgrade
    ```

3. 무선마우스 느림 해결  
   무선마우스 연결시 움직임이 매우 버벅거리는 현상이 발생했다.  
   /boot/cmllint.txt에 `usbhid.mousepoll=4` 입력 (0~8 정도 입력)

4. HDMI 4K 60Hz 설정과 WIFI 간섭  
   이전 라즈베리파이와 달리, 별도 설정없이 HDMI 4K 60Hz 설정이 가능하다.  
   (모니터와 HDMI 케이블 사양 만족시)  
   하지만 내 경우에 HDMI 4K 60Hz 설정시 인터넷이 안되는 문제가 발생했다.
   구글링 결과, HDMI와 WIFI의 간섭으로 발생할 수 있으며, HDMI 케이블 교체로 해결될 수 있다고 한다.
   나는 공유기의 WIFI 주파수를 2.4GHz에서 5GHz로 변경해서 간섭을 피했다.

5. Raspberry Pi Active Cooler 팬 동작 조건  
    ```
    As the temperature of the Raspberry Pi increases, the fan reacts in the following way:

        below 50°C, the fan does not spin at all (0% speed)
        at 50°C, the fan turns on at a low speed (30% speed)
        at 60°C, the fan speed increases to a medium speed (50% speed)
        at 67.5°C, the fan speed increases to a high speed (70% speed)
        at 75°C the fan increases to full speed (100% speed)

    The same mapping of temperature ranges to fan speeds applies to temperature decreases as well, with a 5°C hysteresis; fan speed decreases when the temperature drops to 5°C below each of the above thresholds.
    ```
    출처 : https://www.raspberrypi.com/documentation/computers/raspberry-pi-5.html#cooling-raspberry-pi-5  
    참고 : https://www.raspberrypi.com/news/heating-and-cooling-raspberry-pi-5/  

6. 전원 비교  
   라즈베리파이 5의 전원 요구사양은 5V, 5A 이다. 하지만 한국에는 정품 어뎁터가 아직 출시하지 않았다. (23년 12월 말 기준)  
   라즈베리파이 4의 정품 어뎁터(5V/3A)와 USB PD 3.0 어뎁터를 비교 사용한 결과, 정품 어뎁터 사용시 라즈베리파이 5가 조금 더 안정적으로 동작함을 알 수 있었다.



