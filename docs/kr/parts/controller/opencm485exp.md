---
layout: archive
lang: kr
ref: opencm485exp
read_time: true
share: true
author_profile: false
permalink: /docs/kr/parts/controller/opencm485exp/
sidebar:
  title: OpenCM 485 EXP
  nav: "opencm485exp"
---

# [개요](#개요)

![](/assets/images/parts/controller/opencm904/opencm485exp_product.jpg)

# [주요 사양](#주요-사양)

|      항목       |          설명           |
|:---------------:|:-----------------------:|
|    입력전압     |         5 ~ 30V         |
|      전원       | SMPS, LiPo, DXL PRO 24V |
|   전원 스위치   |            1            |
| 다이나믹셀 포트 |   4Pin x 5, 3Pin x 5    |
|      버튼       |            2            |
|       LED       |            5            |
|      크기       |     68 mm X 66.5 mm     |
|      무게       |           32g           |
|   Serial3 TX    |       헤더 핀 #24       |
|   Serial3 RX    |       헤더 핀 #25       |
|  통신방향 제어  |       헤더 핀 #22       |


# [각 부 명칭](#각-부-명칭)

![](/assets/images/parts/controller/opencm904/opencm485exp_01.jpg)

1. **SMPS DC Adapter** : SMPS DC Adapter를 연결해 OpenCM 485 확장보드 보드에 전원을 인가합니다.
2. **DXL Pro Power** : 다이나믹셀 프로와 동일한 24V 전원 커넥터로 전원을 인가합니다.
3. **Li-Po battery** : 11.1V Li-Po battery(LBS-10)를 사용하는 커넥터 입니다.
4. **Dynamixel TTL 3 PIN** : 3핀 케이블(Dynamixel TTL Bus)을 사용하는 다이나믹셀을 Daisy chain으로 연결하기 위한 포트 입니다.
5. **User Button** : 사용자가 제어 할 수 있는 스위치 입니다.
6. **User LED** : 사용자가 제어 할 수있는 LED 입니다.
7. **I/O header** : OpenCM9.04와 연결하 기 위한 헤더 입니다.(2.54mm pitch)
8. **Dynamixel 485 4 PIN** : 4핀 케이블(Dynamixel 485 Bus)을 사용하는 다이나믹셀을 Daisy chain으로 연결하기 위한 포트 입니다.
9. **Power Switch** : 보드와 다이나믹셀 전원을 on/off하는 스위치 입니다. 단, USB 연결시 보드 전원은 on/off되지 않습니다.
10. **JP1 Jumper** : OpenCM 485 EXP 보드에  입력된 전압을 OpenCM9.04에도 전압을 입력할지 결정하는 점퍼 입니다.

{% include kr/dxl/pinout_warning.md %}

# [OpenCM9.04와 연결하기](#opencm904와-연결하기)

1. OpenCM 485 확장보드 와 OpenCM9.04를 준비합니다. OpenCM9.04는 타입에 관계없이 사용가능하고 헤더를 납땜해주세요.

    ![](/assets/images/parts/controller/opencm904/opencm485.png)

2. OpenCM 485 확장보드 와 OpenCM9.04를 아래의 그림과 같이 연결 합니다.

    **주의** : 방향을 위와 같이 연결 해주시기 바랍니다.
    {: .notice--warning}

    ![](/assets/images/parts/controller/opencm904/img_3483.jpg)

3. OpenCM9.04에 USB Cable를 연결 합니다.

    ![](/assets/images/parts/controller/opencm904/opencm485exp_04.jpg)

4. 다이나믹셀과 SMPS를 연결 합니다.

    ![](/assets/images/parts/controller/opencm904/opencm485exp_05.jpg)

**참고**: 다이나믹셀 펌웨어 업데이트 및 복구시 OpenCM9.04와 OpenCM 485 확장보드를 반드시 분리해주세요
{: .notice--warning}


# [전원 연결 회로](#전원-연결-회로)

OpenCM 485 확장보드 와 OpenCM9.04 연결시 전원 블록 다이어그램  
OpenCM 485 확장보드는 기본적으로 OpenCM9.04 5V 전원 공급을 하며, JP1은 아래 OpeCM 485 확장보드에서 VDD전원을 OpenCM9.04로 공급할 것인지 결정합니다.

![](/assets/images/parts/controller/opencm904/opencm485exp_06.png)

> OpenCM 485 EXP 전원 연결도

OpenCM 485 확장보드의 TTL/485 버스는 OpenCM9.04의 USART3(Serial3)을 통해서 다이나믹셀 버스가 구성됩니다.

**참고**: OpenCM9.04의 다이나믹셀 TTL BUS는 USART1(Serial1)과 연결되어 있습니다.
{: .notice}

![](/assets/images/parts/controller/opencm904/opencm485exp_3.png)

> OpenCM9.04 & OpenCM 485 확장보드 버스 연결도

# [OpenCM 485 확장보드 프로그래밍](#opencm-485-확장보드-프로그래밍)

OpenCM 485 확장보드를 OpenCM9.04와 연결해서 사용하기 위해서는 아두이노 IDE를 사용해야 합니다.

1. [아두이노 IDE 설치하기]{: .blank}

2. OpenCM 485 확장보드의 485 Bus는 OpenCM9.04에서 Serial3(USART3)를 통해서 패킷을 주고 받습니다.

    - DynamixelSDK를 사용해서 프로그래밍 하는 경우 아래와 같이 Serial3를 사용하도록 설정해야 합니다.

    ```cpp
    #include <DynamixelSDK.h>

    #define DEVICENAME      "3"   //Serial3 포트 사용

    dynamixel::PortHandler *portHandler = dynamixel::PortHandler::getPortHandler(DEVICENAME);
    portHandler->openPort();
    ```

    - DynamixelWorkbench를 사용해서 프로그래밍 하는 경우 아래와 같이 Serial3를 사용하도록 설정합니다.

    ```cpp
    #include <DynamixelWorkbench.h>

    #define DEVICENAME      "3"   //Serial3 포트 사용
    #define BAUDRATE        57600

    DynamixelWorkbench dxl_wb;
    dxl_wb.begin(DEVICE_NAME, BAUDRATE);
    ```

# [버튼 및 LED 활용](#버튼-및-led-활용)

OpenCM 485  확장보드에는 OpenCM9.04의 IO핀과 연결된 버튼 2개와 LED 3개가 제공됩니다.
각 버튼 및 LED와 연결된 OpenCM9.04의 IO 핀번호는 아래의 표에서 확인할 수 있습니다.

||OpenCM9.04 I/O|
|:---:|:---:|
|Button1|16|
|Button2|17|
|LED1|18|
|LED2|19|
|LED3|20|

![](/assets/images/parts/controller/opencm904/opencm485exp_11.jpg)


# [다운로드](#다운로드)

- `다운로드` [SCHEMATIC-OpenCM 485 EXP.pdf]

[아두이노 IDE 설치하기]: /docs/kr/software/arduino_ide/
[SCHEMATIC-OpenCM 485 EXP.pdf]: http://support.robotis.com/ko/baggage_files/opencm/schematic1___opencm_485exp.pdf
