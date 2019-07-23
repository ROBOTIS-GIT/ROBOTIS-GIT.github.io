---
layout: archive
lang: kr
ref: ollo-4
read_time: true
share: true
author_profile: false
permalink: /docs/kr/edu/ollo/ollo-4/
sidebar:
  title: OLLO 4단계
  nav: "ollo-4"
---

# [개요](#개요)

올로 교육키트 (로봇 수업용) 4단계는 제어기를 통한 로봇의 제어 원리부터 서보모터의 제어, 접촉센서와 적외선센서, LED 모듈의 제어 원리를 학습할 수 있습니다.  
로봇 프로그램의 순서도 개념을 이해하고, 프로그래밍 기초 지식을 학습함으로써 실질적이고 본격적인 로봇 제작 및 프로그래밍을 이해하는 단계입니다.  
제작한 로봇을 센서로 동작시키거나 무선조종기로 조종할 수 있는 프로그램을 직접 제작해 봅니다.

올로 교육키트 (로봇 수업용) 4단계는 2단계,3단계 키트와 결합되어 총 12주차의 프로그래밍 학습과 센서들의 활용, 무선 조종 프로그래밍, 원리의 이해, 문제풀이 등의 과정을 제공합니다.  
12회에 걸쳐 로봇을 순서대로 만들면서 로봇 제작의 원리를 학습할 수 있습니다.


**주의** : 올로 4단계는 현재 단종되어 더 이상 판매되지 않습니다.
{: .notice--warning}

올로 교육키트 4단계는 2단계, 3단계 키트의 부품들이 있어야 로봇을 제작할 수 있습니다. 반드시 교육키트 2단계, 3단계를 먼저 구매하시기 바랍니다.  
{: .notice}

# [부품 목록](#부품-목록)


 ![](/assets/images/edu/ollo/edu_4th_partlist_kr.png)

- [고속 감속 모터]

# [작동하기](#작동하기)

## [지그비 무선 조종](#지그비-무선-조종)

### 지그비(ZIGBee)

![](/assets/images/edu/ollo/zig_100_110_kr.png)

[ZIG-100/110]은 로봇용 무선 통신 장치로서 ZIGBee 방식을 사용합니다. ZIGBee 는 Bluetooth 와 같이 PAN(Personal Area Network) 통신에 많이 사용되는 통신 기술입니다.  
적외선 방식에 비해서 통신 품질이 매우 좋고, 여러 명이 동시에 조종하여도 각자 자신의 로봇을 조종할 수 있는 장점이 있습니다.

구매한 제품에 지그비 모듈이 포함되지 않을 수 있습니다. 이 경우에는 별도로 구매해야 합니다. BT-210도 사용법은 동일합니다.
{: .notice}

### 제어기와 지그비

RC-100 을 이용한 올로와 바이올로이드의 조종은 기본적으로 적외선 방식의 무선 통신을 이용하도록 되어 있습니다.  
이것을 ZIGBee 방식의 무선 통신을 이용하도록 하기 위해서는 [ZIG-110 set] 를 별도로 구매하여 [RC-100] 에 ZIG-100 을 장착하고, [제어기]에 ZIG-110 을 장착해야 합니다.  
(자세한 장착 방법은 각 부품의 설명 페이지를 참고하세요.)

지그비 셋트는 제품 출하시 서로 통신이 가능하도록 설정이 맞춰져 있습니다. 만약, 다른 지그비 셋트와 혼용하면 무선 조종이 되지 않으니 섞이지 않도록 주의하시기 바랍니다.   
{: .notice--warning}

|RC-100 에 ZIG-100 모듈을 장착한 모습|CM-100 에 ZIG-110 모듈을 장착한 모습|
|:-----:|:-----:|
|![](/assets/images/edu/ollo/rc-100_zig-100_insert4_kr.jpg)|![](/assets/images/edu/ollo/cm100_zig110_kr.jpg)|

|CM-510 에 ZIG-110 모듈을 장착한 모습|CM-5 에 ZIG-100 모듈을 장착한 모습|
|:-----:|:-----:|
|![](/assets/images/edu/ollo/cm510_zig110_kr.png)|![](/assets/images/edu/ollo/cm5_zig100_kr.png)|


# [다운로드](#다운로드)

## [교안 예제(교육키트 4단계)](#교안-예제(교육키트-4단계))

각 예제의 조립 방법이나 실행 시 동작에 관한 내용은 교육키트 4단계 교안을 참고하세요.   
또한, 예제 태스크 코드의 다운로드 방법은 [태스크 코드 다운로드]를 참고하세요.  
{: .notice}

|I-1|태스크 코드|설명|
| :---: | :-----: | :--- |
|1. 로봇 축구<br />![](/assets/images/edu/ollo/l4_hockey_kr.jpg)|[Download][OLLO_L4_SoccerASM_KR.tsk]<br />[Download][OLLO_L4_Soccer_KR.tsk]|-조립 확인용 예제 프로그램<br />- 로봇 예제 프로그램|
|2. 라인트레이서<br /> ![](/assets/images/edu/ollo/l4_line-tracer_kr.jpg)|[Download][OLLO_L4_LinetracerASM_KR.tsk]<br />[Download][OLLO_L4_Linetracer_KR.tsk]|-조립 확인용 예제 프로그램<br />- 로봇 예제 프로그램|
|3. 로봇 얼굴<br />![](/assets/images/edu/ollo/l4_face_kr.jpg)|[Download][OLLO_L4_FaceASM_KR.tsk]<br />[Download][OLLO_L4_FaceExam_KR.tsk]<br />[Download][OLLO_L4_Face_KR.tsk]|-조립 확인용 예제 프로그램<br />-프로그래밍 예제 프로그램<br />- 로봇 예제 프로그램|
|4. 미로 탈출 로봇<br />![](/assets/images/edu/ollo/l4_micro-mouse_kr.jpg)|[Download][CM100_L4_MicroMouseASM_KR.tsk]<br />[Download][OLLO_L4_MicroMouse_KR.tsk]<br />|-조립 확인용 예제 프로그램<br />- 로봇 예제 프로그램|

|I-2|태스크 코드|설명|
| :---: | :-----: | :--- |
|5. 회전목마<br />![](/assets/images/edu/ollo/l4_carousel_kr.jpg)|[Download][OLLO_L4_CarouselASM_KR.tsk]<br />[Download][OLLO_L4_CarouselExam1_KR.tsk]<br />[Download][OLLO_L4_CarouselExam2_KR.tsk]<br />[Download][OLLO_L4_Carousel_KR.tsk]|-조립 확인용 예제 프로그램<br />-프로그래밍 예제 프로그램<br />-프로그래밍 예제 프로그램2<br />- 로봇 예제 프로그램|
|6. 탐사 로봇<br />![](/assets/images/edu/ollo/l4_gripper_kr.jpg)|[Download][OLLO_L4_ExplorerASM_KR.tsk]<br />[Download][OLLO_L4_Explorer_KR.tsk]|-조립 확인용 예제 프로그램<br />- 로봇 예제 프로그램|
|7. 지게차<br />![](/assets/images/edu/ollo/l4_forklift_kr.jpg)|[Download][OLLO_L4_ForkliftASM_KR.tsk]<br />[Download][OLLO_L4_Forklift_KR.tsk]|-조립 확인용 예제 프로그램<br />- 로봇 예제 프로그램|
|8. 전투 로봇<br />![](/assets/images/edu/ollo/l4_war_robot_kr.jpg)|[Download][OLLO_L4_WarRobotASM_KR.tsk]<br />[Download][OLLO_L4_WarRobot_KR.tsk]|-조립 확인용 예제 프로그램<br />- 로봇 예제 프로그램|

|I-3|태스크 코드|설명|
| :---: | :-----: | :--- |
|9. 덤프 트럭<br />![](/assets/images/edu/ollo/l4_truck_kr.jpg)|[Download][OLLO_L4_DumpTruckASM_KR.tsk]<br />[Download][OLLO_L4_DumpTruck_KR.tsk]|-조립 확인용 예제 프로그램<br />- 로봇 예제 프로그램|
|10. 춤추는 로봇<br />![](/assets/images/edu/ollo/l4_dancer_kr.jpg)|[Download][OLLO_L4_DanceRobotASM_KR.tsk]<br />[Download][OLLO_L4_DanceRobotExam_KR.tsk]<br />[Download][OLLO_L4_DanceRobot_KR.tsk]|-조립 확인용 예제 프로그램<br />-프로그래밍 예제 프로그램<br />- 로봇 예제 프로그램|
|11. 줄타는 원숭이<br />![](/assets/images/edu/ollo/l4_ropedancer_kr.jpg)|[Download][OLLO_L4_MonkeyASM_KR.tsk]<br />[Download][OLLO_L4_Monkey_KR.tsk]|-조립 확인용 예제 프로그램<br />- 로봇 예제 프로그램|
|12. 토끼와 거북이<br />![](/assets/images/edu/ollo/l4_rabbit_turtle_kr.jpg)|[Download][OLLO_L4_RabbitTurtleASM_KR.tsk]<br />[Download][OLLO_L4_RabbitTurtle_KR.tsk]|-조립 확인용 예제 프로그램<br />- 로봇 예제 프로그램|


[고속 감속 모터]: /docs/kr/parts/motor/h_speed_geared_motor/
[ZIG-100/110]: /docs/kr/parts/communication/zig-110/
[ZIG-110 set]: /docs/kr/parts/communication/zig-110/
[RC-100]: /docs/kr/parts/communication/rc-100/
[제어기]: /docs/kr/parts/controller/controller_compatibility/
[태스크 코드 다운로드]: /docs/kr/faq/download_task_code/
[OLLO_L4_SoccerASM_KR.tsk]: http://www.robotis.com/service/download.php?no=857
[OLLO_L4_Soccer_KR.tsk]: http://www.robotis.com/service/download.php?no=858
[OLLO_L4_LinetracerASM_KR.tsk]: http://www.robotis.com/service/download.php?no=849
[OLLO_L4_Linetracer_KR.tsk]: http://www.robotis.com/service/download.php?no=850
[OLLO_L4_FaceASM_KR.tsk]: http://www.robotis.com/service/download.php?no=844
[OLLO_L4_FaceExam_KR.tsk]: http://www.robotis.com/service/download.php?no=845
[OLLO_L4_Face_KR.tsk]: http://www.robotis.com/service/download.php?no=846
[CM100_L4_MicroMouseASM_KR.tsk]: http://www.robotis.com/service/download.php?no=851
[OLLO_L4_MicroMouse_KR.tsk]: http://www.robotis.com/service/download.php?no=852
[OLLO_L4_CarouselASM_KR.tsk]: http://www.robotis.com/service/download.php?no=833
[OLLO_L4_CarouselExam1_KR.tsk]: http://www.robotis.com/service/download.php?no=834
[OLLO_L4_CarouselExam2_KR.tsk]: http://www.robotis.com/service/download.php?no=835
[OLLO_L4_Carousel_KR.tsk]: http://www.robotis.com/service/download.php?no=836
[OLLO_L4_ExplorerASM_KR.tsk]: http://www.robotis.com/service/download.php?no=842
[OLLO_L4_Explorer_KR.tsk]: http://www.robotis.com/service/download.php?no=843
[OLLO_L4_ForkliftASM_KR.tsk]: http://www.robotis.com/service/download.php?no=847
[OLLO_L4_Forklift_KR.tsk]: http://www.robotis.com/service/download.php?no=848
[OLLO_L4_WarRobotASM_KR.tsk]: http://www.robotis.com/service/download.php?no=859
[OLLO_L4_WarRobot_KR.tsk]: http://www.robotis.com/service/download.php?no=860
[OLLO_L4_DumpTruckASM_KR.tsk]: http://www.robotis.com/service/download.php?no=840
[OLLO_L4_DumpTruck_KR.tsk]: http://www.robotis.com/service/download.php?no=841
[OLLO_L4_DanceRobotASM_KR.tsk]: http://www.robotis.com/service/download.php?no=837
[OLLO_L4_DanceRobotExam_KR.tsk]: http://www.robotis.com/service/download.php?no=838
[OLLO_L4_DanceRobot_KR.tsk]: http://www.robotis.com/service/download.php?no=839
[OLLO_L4_MonkeyASM_KR.tsk]: http://www.robotis.com/service/download.php?no=853
[OLLO_L4_Monkey_KR.tsk]: http://www.robotis.com/service/download.php?no=854
[OLLO_L4_RabbitTurtleASM_KR.tsk]: http://www.robotis.com/service/download.php?no=855
[OLLO_L4_RabbitTurtle_KR.tsk]: http://www.robotis.com/service/download.php?no=856
