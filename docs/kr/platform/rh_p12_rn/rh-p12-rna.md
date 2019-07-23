---
layout: archive
lang: kr
ref: rh_p12_rna
read_time: true
share: true
author_profile: false
permalink: /docs/kr/platform/rh_p12_rna/
sidebar:
  title: RH-P12-RN(A)
  nav: "rh_p12_rna"
product_group: rh_p12_rna
---

# [개요](#개요)

![](/assets/images/platform/rh_p12_rn/rh-p12-rn_product.png)

> RH_P12_RN(A)

# [주요 사양](#주요-사양)

| 항목                | 사양                                                                                           |
|:--------------------|:-----------------------------------------------------------------------------------------------|
| MCU                 | ST CORTEX-M4 (STM32F405 @ 168Mhz, 32bit)                                                       |
| 위치 센서           | Contactless Absolute Encoder (12bit, 360&deg;)<br />Maker : ams(www.ams.com), Part No : AS5045 |
| 모터                | Coreless                                                                                       |
| 통신 속도           | 9,600 bps ~ 10.5 Mbps                                                                          |
| 제어 알고리즘       | PID Control                                                                                    |
| 정밀도              | 0.088&deg;                                                                                     |
| 동작 모드           | 전류제어 모드<br />전류기반 위치제어 모드                                                      |
| 무게                | 500g                                                                                           |
| 스트로크            | 0 ~ 109mm                                                                                      |
| 감속비              | 1181 : 1                                                                                       |
| 최대 파지력         | 170N                                                                                           |
| 권장 가반하중       | 5kg                                                                                            |
| 동작 온도           | -5&deg;C ~ 55&deg;C                                                                            |
| 사용 전압           | 24V                                                                                            |
| Command Signal      | Digital Packet                                                                                 |
| Protocol Type       | RS485 Asynchronous Serial Communication<br />(8bit, 1stop, No Parity)                          |
| Physical Connection | RS485 Multidrop Bus                                                                            |
| ID                  | 0 ~ 252                                                                                        |
| Feedback            | Position, Velocity, Current, Temperature, Input Voltage, etc                                   |
| Material            | Full Metal Gear, Metal Body                                                                    |
| Standby Current     | 30mA                                                                                           |
| Peak Current        | 3.33A                                                                                          |

{% include kr/dxl/warning.md %}

{% include kr/dxl/control_table.md %}

## [EEPROM 영역](#eeprom-영역)

| 주소 | 크기<br>(Byte) | 명칭                                        | 접근 | 기본값 |     범위      |          단위           |
|:----:|:--------------:|:--------------------------------------------|:----:|:------:|:-------------:|:-----------------------:|
|  0   |       2        | [Model Number](#model-number)               |  R   | 35,074 |       -       |            -            |
|  2   |       4        | [Model Information](#model-information)     |  R   |   -    |       -       |            -            |
|  6   |       1        | [Firmware Version](#firmware-version)       |  R   |   -    |       -       |            -            |
|  7   |       1        | [ID](#id)                                   |  RW  |   1    |    0 ~ 252    |            -            |
|  8   |       1        | [Baud Rate](#baud-rate)                     |  RW  |   1    |     0 ~ 9     |            -            |
|  9   |       1        | [Return Delay Time](#return-delay-time)     |  RW  |  250   |    0 ~ 255    |        2 [μsec]         |
|  11  |       1        | [Operating Mode](#operating-mode)           |  RW  |   5    |     0, 5      |            -            |
|  12  |       1        | [Sencondary ID](#secondary-id)              |  RW  |  255   |    0 ~ 255    |            -            |
|  20  |       4        | [Homing Offset](#homing-offset)             |  RW  |   0    |   0 ~ 1,150   |        1 [pulse]        |
|  24  |       4        | [Moving Threshold](#moving-threshold)       |  RW  |   80   |   0 ~ 2,970   |     0.01 [rev/min]      |
|  31  |       1        | [Temperature Limit](#temperature-limit)     |  RW  |   80   |    0 ~ 100    |       1 [&deg;C]        |
|  32  |       2        | [Max Voltage Limit](#max-voltage-limit)     |  RW  |  350   |    0 ~ 350    |         0.1 [V]         |
|  34  |       2        | [Min Voltage Limit](#min-voltage-limit)     |  RW  |  150   |    0 ~ 350    |         0.1 [V]         |
|  36  |       2        | [PWM Limit](#pwm-limit)                     |  RW  | 2,009  |   0 ~ 2,009   |            -            |
|  38  |       2        | [Current Limit](#current-limit)             |  RW  | 1,984  |   0 ~ 1,984   |         1 [mA]          |
|  40  |       4        | [Acceleration Limit](#acceleration-limit)   |  RW  | 3,447  | 0 ~ 1,378,788 | 1 [rev/min<sup>2</sup>] |
|  44  |       4        | [Velocity Limit](#velocity-limit)           |  RW  | 2,970  |   0 ~ 2,970   |     0.01 [rev/min]      |
|  48  |       4        | [Max Position Limit](#max-position-limit)   |  RW  | 1,150  |   0 ~ 1,150   |        1 [pulse]        |
|  52  |       4        | [Min Position Limit](#min-position-limit)   |  RW  |   0    |   0 ~ 1,150   |        1 [pulse]        |
|  56  |       1        | [External Port Mode 1](#external-port-mode) |  RW  |   3    |     0 ~ 3     |            -            |
|  57  |       1        | [External Port Mode 2](#external-port-mode) |  RW  |   3    |     0 ~ 3     |            -            |
|  58  |       1        | [External Port Mode 3](#external-port-mode) |  RW  |   3    |     0 ~ 3     |            -            |
|  59  |       1        | [External Port Mode 4](#external-port-mode) |  RW  |   3    |     0 ~ 3     |            -            |
|  63  |       1        | [Shutdown](#shutdown)                       |  RW  |   52   |    0 ~ 255    |            -            |
| 168  |       2        | [Indirect Address 1](#indirect-address)     |  RW  |  634   |  512 ~ 1,023  |            -            |
| 170  |       2        | [Indirect Address 2](#indirect-address)     |  RW  |  635   |  512 ~ 1,023  |            -            |
| 172  |       2        | [Indirect Address 3](#indirect-address)     |  RW  |  636   |  512 ~ 1,023  |            -            |
| ...  |      ...       | ...                                         | ...  |  ...   |      ...      |           ...           |
| 422  |       2        | [Indirect Address 128](#indirect-address)   |  RW  |  761   |  512 ~ 1,023  |            -            |

## [RAM 영역](#ram-영역)

| 주소 | 크기<br />(Byte) | 명칭                                              | 접근 | 기본값 |                        범위                         |          단위           |
|:----:|:----------------:|:--------------------------------------------------|:----:|:------:|:---------------------------------------------------:|:-----------------------:|
| 512  |        1         | [Torque Enable](#torque-enable)                   |  RW  |   0    |                        0 ~ 1                        |            -            |
| 513  |        1         | [LED Red](#led-red)                               |  RW  |   0    |                       0 ~ 255                       |            -            |
| 514  |        1         | [LED Green](#led-green)                           |  RW  |   0    |                       0 ~ 255                       |            -            |
| 515  |        1         | [LED Blue](#led-blue)                             |  RW  |   0    |                       0 ~ 255                       |            -            |
| 516  |        1         | [Status Return Level](#status-return-level)       |  RW  |   2    |                        0 ~ 2                        |            -            |
| 517  |        1         | [Registered Instruction](#registered-instruction) |  R   |   0    |                          -                          |            -            |
| 518  |        1         | [Hardware Error Status](#hardware-error-status)   |  R   |   0    |                          -                          |            -            |
| 524  |        2         | [Velocity I Gain](#velocity-i-gain)               |  RW  |   -    |                     0 ~ 32,767                      |            -            |
| 526  |        2         | [Velocity P Gain](#velocity-i-gain)               |  RW  |   -    |                     0 ~ 32,767                      |            -            |
| 528  |        2         | [Position D Gain](#position-p-gain)               |  RW  |   -    |                     0 ~ 32,767                      |            -            |
| 532  |        2         | [Position P Gain](#position-p-gain)               |  RW  |   -    |                     0 ~ 32,767                      |            -            |
| 530  |        2         | [Position I Gain](#position-p-gain)               |  RW  |   -    |                     0 ~ 32,767                      |            -            |
| 536  |        2         | [Feedforward 2nd Gain](#feedforward-2nd-gain)     |  RW  |   -    |                     0 ~ 32,767                      |            -            |
| 538  |        2         | [Feedforward 1st Gain](#feedforward-1st-gain)     |  RW  |   -    |                     0 ~ 32,767                      |            -            |
| 546  |        1         | [Bus Watchdog](#bus-watchdog)                     |  RW  |   -    |                       0 ~ 127                       |        20 [msec]        |
| 548  |        2         | [Goal PWM](#goal-pwm)                             |  RW  |   -    |         -PWM Limit(36) ~<br> PWM Limit(36)          |            -            |
| 550  |        2         | [Goal Current](#goal-current)                     |  RW  |   0    |     -Current Limit(38) ~<br> Current Limit(38)      |         1 [mA]          |
| 552  |        4         | [Goal Velocity](#goal-velocity)                   |  RW  |   0    |    -Velocity Limit(44) ~<br> Velocity Limit(44)     |     0.01 [rev/min]      |
| 556  |        4         | [Profile Acceleration](#profile-acceleration)     |  RW  |   0    |           0 ~<br> Acceleration Limit(40)            | 1 [rev/min<sup>2</sup>] |
| 560  |        4         | [Profile Velocity](#profile-velocity)             |  RW  |   0    |             0 ~<br> Velocity Limit(44)              |     0.01 [rev/min]      |
| 564  |        4         | [Goal Position](#goal-position)                   |  RW  |   -    | Min Position Limit(52) ~<br> Max Position Limit(48) |        1[pulse]         |
| 568  |        2         | [Realtime Tick](#realtime-tick)                   |  R   |   -    |                     0 ~ 32,767                      |        1 [msec]         |
| 570  |        1         | [Moving](#moving)                                 |  R   |   -    |                          -                          |            -            |
| 571  |        1         | [Moving Status](#moving-status)                   |  R   |   -    |                          -                          |            -            |
| 572  |        2         | [Present PWM](#present-pwm)                       |  R   |   -    |                          -                          |            -            |
| 574  |        2         | [Present Current](#present-current)               |  R   |   -    |                          -                          |         1 [mA]          |
| 576  |        4         | [Present Velocity](#present-velocity)             |  R   |   -    |                          -                          |     0.01 [rev/min]      |
| 580  |        4         | [Present Position](#present-position)             |  R   |   -    |                          -                          |        1 [pulse]        |
| 584  |        4         | [Velocity Trajectory](#velocity-trajectory)       |  R   |   -    |                          -                          |     0.01 [rev/min]      |
| 588  |        4         | [Position Trajectory](#position-trajectory)       |  R   |   -    |                          -                          |        1 [pulse]        |
| 592  |        2         | [Present Input Voltage](#present-input-voltage)   |  R   |   -    |                          -                          |         0.1 [V]         |
| 594  |        1         | [Present Temperature](#present-temperature)       |  R   |   -    |                          -                          |       1 [&deg;C]        |
| 600  |        2         | [External Port Data 1](#external-port-data)       | R/RW |   0    |                      0 ~ 4,095                      |            -            |
| 602  |        2         | [External Port Data 2](#external-port-data)       | R/RW |   0    |                      0 ~ 4,095                      |            -            |
| 604  |        2         | [External Port Data 3](#external-port-data)       | R/RW |   0    |                      0 ~ 4,095                      |            -            |
| 606  |        2         | [External Port Data 4](#external-port-data)       | R/RW |   0    |                      0 ~ 4,095                      |            -            |
| 634  |        1         | [Indirect Data 1](#indirect-data)                 |  RW  |   0    |                       0 ~ 255                       |            -            |
| 635  |        1         | [Indirect Data 2](#indirect-data)                 |  RW  |   0    |                       0 ~ 255                       |            -            |
| 636  |        1         | [Indirect Data 3](#indirect-data)                 |  RW  |   0    |                       0 ~ 255                       |            -            |
| ...  |       ...        | ...                                               | ...  |  ...   |                         ...                         |           ...           |
| 761  |        1         | [Indirect Data 128](#indirect-data)               |  RW  |   0    |                       0 ~ 255                       |            -            |


## [컨트롤 테이블 설명](#컨트롤-테이블-설명)

**주의**: EEPROM Area에 존재하는 모든 Data는 Torque Enable(512)의 값이 `0` 일 때만 변경할 수 있습니다.
{: .notice--warning}

**주의**: RH-P12-RN(A)는 RH-P12-RN의 개선된 firmware 입니다. 두 firmware의 Control table이 다르니, 사용 전에 Control table의 주소를 필히 확인해 주세요.
{: .notice}

### <a name="model-number"></a>**[Model Number(0)](#model-number0)**
RH-P12-RN(A)의 모델 번호입니다.

|    모델명    |  Model Number   |
|:------------:|:---------------:|
| RH-P12-RN(A) | 35,074 (0x8902) |

### <a name="firmware-version"></a>**[Firmware Version(6)](#firmware-version6)**
{% include kr/dxl/pro_plus/control_table_6_firmware_version.md %}

### <a name="id"></a>**[ID(7)](#id7)**
{% include kr/dxl/pro_plus/control_table_7_id.md %}

### <a name="baud-rate"></a>**[Baud Rate(8)](#baud-rate8)**
{% include kr/dxl/pro_plus/control_table_8_baud_rate.md %}

### <a name="return-delay-time"></a>**[Return Delay Time(9)](#return-delay-time9)**
{% include kr/dxl/pro_plus/control_table_9_return_delay_time.md %}

### <a name="operating-mode"></a>**[Operating Mode(11)](#operating-mode11)**
장치의 제어 모드를 설정합니다. 각 제어 모드마다 특성이 다르기 때문에, 구현하려는 시스템에 적합한 제어 모드를 설정하시기 바랍니다.

| 값         | 동작 모드              | 설명                                            |
|:-----------|:-----------------------|:------------------------------------------------|
| 0          | 전류제어 모드          | 속도와 위치는 제어하지 않고, 전류를 제어합니다. |
| 1 ~ 4      | Reserved               | -                                               |
| 5(Default) | 전류기반 위치제어 모드 | 위치와 전류를 제어합니다.                       |

### <a name="secondary-id"></a>**[Secondary ID(12)](#secondary-id12)**
{% include kr/dxl/pro_plus/control_table_12_secondary_id.md %}

### <a name="homing-offset"></a>**[Homing Offset(20)](#homing-offset20)**
0점의 위치를 조절 할 수 있습니다. 이 값은 Present Position(580)에 더해지게 됩니다.
Present Position = 실제 위치 + Homing offset(20) 이 됩니다.

|   단위    | 값의 범위 |
|:---------:|:---------:|
| 1 [pulse] | 0 ~ 1150  |

### <a name="moving-threshold"></a>**[Moving Threshold(24)](#moving-threshold24)**
{% include kr/dxl/pro_plus/control_table_24_moving_threshold.md %}

|      단위      | 값의 범위 |
|:--------------:|:---------:|
| 0.01 [rev/min] | 0 ~ 2,970 |

### <a name="temperature-limit"></a>**[Temperature Limit(31)](#temperature-limit31)**
{% include kr/dxl/pro_plus/control_table_31_temperature_limit.md %}

### <a name="max-voltage-limit"></a><a name="min-voltage-limit"></a>**[Max/Min Voltage Limit(32, 34)](#maxmin-voltage-limit32-34)**
{% include kr/dxl/pro_plus/control_table_32_voltage_limit.md %}

### <a name="pwm-limit"></a>**[PWM Limit(36)](#pwm-limit36)**
{% include kr/dxl/pro_plus/control_table_36_pwm_limit.md %}

### <a name="current-limit"></a>**[Current Limit(38)](#current-limit38)**
목표 전류 값의 한계 값입니다. Goal Current(550)은 이 값보다 큰 값을 쓸 수 없습니다. 이 값보다 큰 값을 쓰려 하면, 값이 써지지 않고, Status packet의 error 에 Limit error bit가 set 됩니다.

|  단위  | 값의 범위 |
|:------:|:---------:|
| 1 [mA] | 0 ~ 1,984 |

### <a name="acceleration-limit"></a>**[Acceleration Limit(40)](#acceleration-limit40)**
프로파일 가속도 값의 한계 값입니다. Profile Acceleration(556)은 이 값보다 큰 값을 쓸 수 없습니다. 이 값보다 큰 값을 쓰려 하면, 값이 써지지 않고, Status packet의 error 에 Limit error bit가 set 됩니다.

|          단위           |   값의 범위   |
|:-----------------------:|:-------------:|
| 1 [rev/min<sup>2</sup>] | 0 ~ 1,378,788 |

### <a name="velocity-limit"></a>**[Velocity Limit(44)](#velocity-limit44)**
목표 속도 값과 프로파일 속도 값의 한계 값입니다. Goal Velocity(552)와 Profile Velocity(560)는 이 값보다 큰 값을 쓸 수 없습니다. 이 값보다 큰 값을 쓰려 하면, 값이 써지지 않고, Status packet의 error 에 Limit error bit가 set 됩니다.

|      단위      | 값의 범위 |
|:--------------:|:---------:|
| 0.01 [rev/min] | 0 ~ 2,970 |

### <a name="max-position-limit"></a><a name="min-position-limit"></a>**[Max/Min Position Limit(48, 52)](#maxmin-position-limit48-52)**
전류 기반 위치 제어 모드에서 목표 위치의 제한 값으로써, 0 ~ 1,150 범위 내에서 목표 위치를 제한 합니다.  
따라서 위치 제어 모드에서 Goal position(564)은 이 값보다 클 수 없습니다. 이 값보다 큰 값을 쓰려 하면, 값이 써지지 않고, Status packet의 error 에 Limit error bit가 set 됩니다.

|   단위    | 값의 범위 |
|:---------:|:---------:|
| 1 [pulse] | 0 ~ 1,150 |

### <a name="external-port-mode"></a><a name="external-port-data"></a>**[External Port Mode](#external-port-mode)**, **[External Port Data](#external-port-data)**
{% include kr/dxl/pro_plus/control_table_56_external_port.md %}

### <a name="shutdown"></a>**[Shutdown(63)](#shutdown63)**
{% include kr/dxl/pro_plus/control_table_63_shutdown.md %}

### <a name="indirect-address"></a><a name="indirect-data"></a>**[Indirect Address](#indirect-address)**, **[Indirect Data](#indirect-data)**
{% include kr/dxl/pro_plus/control_table_168_indirect.md %}

### <a name="torque-enable"></a>**[Torque Enable(512)](#torque-enable512)**
{% include kr/dxl/control_table_torque_enable.md %}

### <a name="led"></a>**[RGB LED](#rgb-led)**
{% include kr/dxl/pro_plus/control_table_513_led.md %}

### <a name="status-return-level"></a>**[Status Return Level(516)](#status-return-level516)**
{% include kr/dxl/pro_plus/control_table_516_status_return_level.md %}

### <a name="registered-instruction"></a>**[Registered Instruction(517)](#registered-instruction517)**
{% include kr/dxl/pro_plus/control_table_517_registered_instruction.md %}

### <a name="hardware-error-status"></a>**[Hardware Error Status(518)](#hardware-error-status518)**
{% include kr/dxl/pro_plus/control_table_518_hardware_error_status.md %}

### <a name="velocity-i-gain"><a name="position-p-gain"></a><a name="feedforward-2nd-gain"></a><a name="feedforward-1st-gain"></a>**[Velocity PI Gain(524, 526), Position PID Gain(528,530,532), Feedforward 2nd Gains(536), Feedforward 1st Gains(538)](#velocity-pi-gain524-526, #position-pid-gain528-530-532, Feedforward 2nd Gains536, Feedforward 1st Gains538)**
전류기반 위치 제어 모드에서 동작하는 위치 제어기의 Gain입니다. 편의상 장치 내부 제어기의 Position P Gain을 K<sub>P</sub>P로 표기하고 Control Table의 Gain은 K<sub>P</sub>P<sub>(TBL)</sub>로 표기합니다.

|                           |    제어기 Gain    |                범위 | 설명                 |
|:-------------------------:|:-----------------:|:------------------------------------------:|
|   Velocity I Gain(524)    |  K<sub>V</sub>I   |    0 ~ 32,767 | Velocity Integral Gain     |
|   Velocity P Gain(526)    |  K<sub>V</sub>P   |   0 ~ 32,767 | Velocity Proportion Gain    |
|   Position D Gain(528)    |  K<sub>P</sub>D   |  0 ~ 32,767 | Position Differential Gain   |
|   Position I Gain(530)    |  K<sub>P</sub>I   |    0 ~ 32,767 | Position Integral Gain     |
|   Position P Gain(532)    |  K<sub>P</sub>P   |   0 ~ 32,767 | Position Proportion Gain    |
| Feedforward 2nd Gain(536) | K<sub>FF1st</sub> | 0 ~ 32,767 | Feedforward Acceleration Gain |
| Feedforward 1st Gain(538) | K<sub>FF1st</sub> |   0 ~ 32,767 | Feedforward Velocity Gain   |

다음은 전류기반 위치 제어 모드에서 동작하는 위치제어기의 블록다이어그램입니다. 사용자의 요청이 장치에 전달된 후, 장치의 Horn이 구동되기까지의 과정은 다음과 같습니다.

1. 사용자의 요청이 통신 버스를 통해 Goal Position(564)에 등록됩니다.
2. Goal Position은 Profile Velocity(560)와 Profile Acceleration(556)에 의해서 목표 위치 궤적과 목표 속도 궤적으로 변경됩니다.
3. 목표 속도 궤적과 목표 위치 궤적은 Velocity Trajectory(584), Position Trajectory(588)에 표기됩니다.
4. Feedforward와 PID 제어기는 목표 궤적을 입력받아 모터에 인가할 PWM 출력을 계산합니다.
5. Goal PWM(548)은 계산된 PWM 출력을 제한하여 최종 PWM값을 결정합니다.
6. 최종 PWM값은 Inverter를 통해 모터에 적용되고 장치의 Horn이 구동됩니다.
7. 구동 결과는 Present Position(580), Present Velocity(576), Present PWM(572), Present Current(574)에 표기됩니다.

![](/assets/images/platform/rh_p12_rn/rh_p12_rn_a_position.png)

**참고** : K<sub>a</sub>는 Anti-windup Gain로서 사용자가 변경할 수는 없습니다.
{: .notice}

### <a name="bus-watchdog"></a>**[Bus Watchdog(546)](#bus-watchdog546)**
{% include kr/dxl/pro_plus/control_table_546_bus_watchdog.md %}

### <a name="goal-pwm"></a>**[Goal PWM(548)](#goal-pwm548)**
{% include kr/dxl/pro_plus/control_table_548_goal_pwm.md %}

### <a name="goal-current"></a>**[Goal Current(550)](#goal-current550)**
전류 제어 모드에서는 목표 전류값으로 동작하고, 전류기반 위치 제어 모드에서는 전류 제어기 입력(전류)의 제한값으로 동작됩니다.
이 값은 Current Limit(38) 보다 큰 값을 쓸 수 없습니다.

### <a name="goal-velocity"></a>**[Goal Velocity(552)](#goal-velocity552)**
속도 제어기 입력(속도)의 제한값으로 동작됩니다.
이 값은 Velocity Limit(44) 보다 큰 값을 쓸 수 없습니다.  

### <a name="profile-acceleration"></a>**[Profile Acceleration(556)](#profile-acceleration556)**
프로파일 가속도를 설정합니다. 동작모드가 전류기반 위치 제어 모드에서만 사용할 수 있습니다.  프로파일 가속도 값의 범위는 0 ~ Acceleration Limit(40) 입니다.

**주의** : Profile Velocity(560) 의 값이 `0` 일 때는 프로파일 가속도가 적용되지 않습니다.
{: .notice}


### <a name="profile-velocity"></a>**[Profile Velocity(560)](#profile-velocity560)**
Profile의 최대 속도를 설정합니다.  
Profile Velocity(560)는 전류기반 위치 제어 모드에서만 적용 가능합니다.  
Profile Velocity(560)는 Velocity Limit(44)보다 클 수 없습니다.  
참고로 속도 제어 모드에서는 Profile Velocity(560)는 적용되지 않고 Profile Acceleration(556)만 적용됩니다.

|      단위      |          범위          |                            설명                             |
|:--------------:|:----------------------:|:-----------------------------------------------------------:|
| 0.01 [rev/min] | 0 ~ Velocity Limit(44) | Profile Velocity(560)이 ‘0’인 경우, 무한대 속도를 뜻합니다. |

Profile이란 모터 구동 시 급격하게 변하는 속도와 가속도를 조절함으로써 진동, 소음 및 모터의 부하를 줄이는 가감속 제어 방법입니다.  
일반적으로 속도에 근거하여 가감속을 제어하기 때문에 Velocity Profile이라고 불립니다.  
장치는 3가지 형태의 Profile을 제공합니다. 다음은 3가지 종류의 Profile을 표시합니다.  
기본적으로 Profile의 선택은 Profile Velocity(560)와 Profile Acceleration(556)의 조합에 의해서 결정됩니다.  
예외적으로 Trapezoidal Profile은 총 이동거리(ΔPos, 목표위치와 현재위치의 차이)가 추가로 고려되어 선택됩니다.  

![](/assets/images/dxl/pro_plus/profile_types.png)


장치의 Profile은 Goal Position(564)이 주어졌을 때, 현재 속도(Profile의 시작속도)를 기반으로 목표 속도 궤적을 생성합니다.  
따라서 장치가 Goal Position(564)로 이동하는 중에 새로운 Goal Position(564)로 목표위치가 변경되어도, 속도의 연속성을 유지하면서 목표 속도 궤적을 생성합니다.  
이와 같이 속도의 불연속이 발생하지 않도록 목표 속도 궤적을 생성하는 기능을 Velocity Override라고 합니다.  
여기서는 수식의 단순화를 위해 Profile의 시작속도를 ‘0’으로 가정합니다.


다음은 Goal Position(564) 명령에 대한 Profile의 동작 과정을 나타냅니다.

1. 사용자의 요청이 통신 버스를 통해 Goal Position(564)에 등록됩니다.
2. Profile Velocity(560)와 Profile Acceleration(556)에 의해서 가속 시간(t1)이 결정됩니다.  
3. Profile Velocity(560), Profile Acceleration(556) 그리고 총 이동거리(ΔPos, 목표 위치와 현재 위치의 차이)에 의해서 Profile의 형태가 다음과 같이 결정됩니다.
4. 최종 선정된 Profile의 형태는 Moving Status(571)에 표기됩니다.(Moving Status(571) 참고)
5. 장치는 Profile에 의해 산출된 목표 궤적에 따라 이동하게 됩니다.
6. Profile에 의한 목표 속도 궤적과 목표 위치 궤적은 Velocity Trajectory(584)와 Position Trajectory(588)에 표기됩니다.

| 조건                                                          | 프로파일 형태              |
|:--------------------------------------------------------------|:---------------------------|
| Profile Velocity(560) = 0                                     | 프로파일 미사용(Step 명령) |
| (Profile Velocity(560) ≠ 0) & (Profile Acceleration(556) = 0) | 사각 프로파일              |
| (Profile Velocity(560) ≠ 0) & (Profile Acceleration(556) ≠ 0) | 사다리꼴 프로파일          |

![](/assets/images/dxl/pro_plus/velocity_profile.png)


{% capture group_notice_03 %}
제공되는 Profile의 형태는 Step과 Trapezoidal 2가지 입니다.  
Velocity Override 기능은 동일하게 동작합니다.  
이때의 가속시간(t<sub>1</sub>)은 다음과 같습니다.  
**t<sub>1</sub> = 600 * {Goal Velocity(552) / Profile Acceleration(556)}**
{% endcapture %}

<div class="notice">
  {{ group_notice_03 | markdownify }}
</div>


### <a name="goal-position"></a>**[Goal Position(564)](#goal-position564)**
이동시키고자 하는 곳의 위치 값입니다.  
값의 범위는 Min Position Limit(52) ~ Max Position Limit(48) 이며, 초기값은 0 ~ 1,150 (0x47E) 입니다.

|  모델명   |                         Goal Position = 0                          |                         Goal Position = 740                         |
|:---------:|:------------------------------------------------------------------:|:-------------------------------------------------------------------:|
| RH-P12-RN | ![](/assets/images/platform/rh_p12_rn/rh_p12_rn_position_open.png) | ![](/assets/images/platform/rh_p12_rn/rh_p12_rn_position_close.png) |

### <a name="realtime-tick"></a>**[Realtime Tick(568)](#realtime-tick568)**
{% include kr/dxl/pro_plus/control_table_568_realtime_tick.md %}

### <a name="moving"></a>**[Moving(570)](#moving570)**
{% include kr/dxl/pro_plus/control_table_570_moving.md %}

### <a name="moving-status"></a>**[Moving Status(571)](#moving-status571)**
움직임에 대한 추가적인 정보를 제공합니다. In-Position Bit(0x01)은 전류기반 위치 제어 모드에서만 동작합니다.

|                         |      |                                상세                                |                                                                 설명                                                                  |
|:-----------------------:|:----:|:------------------------------------------------------------------:|:-------------------------------------------------------------------------------------------------------------------------------------:|
|          Bit 7          | 0x80 |                                 -                                  |                                                                미사용                                                                 |
|          Bit 6          | 0x40 |                                 -                                  |                                                                미사용                                                                 |
| Bit 5<br />~<br />Bit 4 | 0x30 | Profile Type(0x30)<br />Profile Type(0x10)<br />Profile Type(0x00) | 사다리꼴 속도 프로파일(Trapezoidal Velocity Profile)<br />사각 속도 프로파일(Rectangular Velocity Profile)<br />프로파일 미사용(Step) |
|          Bit 3          | 0x08 |                                 -                                  |                                                                미사용                                                                 |
|          Bit 2          | 0x04 |                                 -                                  |                                                                미사용                                                                 |
|          Bit 1          | 0x02 |                                 -                                  |                                                                미사용                                                                 |
|          Bit 0          | 0x01 |                            In-Position                             |                                                         목표위치에 도달 경우                                                          |


### <a name="present-pwm"></a>**[Present PWM(572)](#present-pwm572)**
{% include kr/dxl/pro_plus/control_table_572_present_pwm.md %}

### <a name="present-current"></a>**[Present Current(574)](#present-current574)**
{% include kr/dxl/pro_plus/control_table_574_present_current.md %}

### <a name="present-velocity"></a>**[Present Velocity(576)](#present-velocity576)**
{% include kr/dxl/pro_plus/control_table_576_present_velocity.md %}

### <a name="present-position"></a>**[Present Position(580)](#present-position580)**
장치의 현재 위치 값입니다.

|  모델명   |                         Goal Position = 0                          |                         Goal Position = 740                         |
|:---------:|:------------------------------------------------------------------:|:-------------------------------------------------------------------:|
| RH-P12-RN | ![](/assets/images/platform/rh_p12_rn/rh_p12_rn_position_open.png) | ![](/assets/images/platform/rh_p12_rn/rh_p12_rn_position_close.png) |

### <a name="velocity-trajectory"></a>**[Velocity Trajectory(584)](#velocity-trajectory584)**
Profile에 의해 생성된 목표 속도 궤적입니다. 자세한 사항은 [Profile Velocity(560)]를 참고하세요.

**전류기반 위치 제어 모드** : Position Trajectory(588)을 생성하기 위한 목표 속도 궤적입니다. Profile이 종료되면 Velocity Trajectory(584)은 '0'이 됩니다.


### <a name="position-trajectory"></a>**[Position Trajectory(588)](#position-trajectory588)**
Profile에 의해 생성된 목표 위치 궤적입니다. 전류기반 위치 제어 모드에서만 동작 합니다. 자세한 사항은 [Profile Velocity(560)]를 참고하세요.


### <a name="present-input-voltage"></a>**[Present Input Voltage(592)](#present-input-voltage592)**
{% include kr/dxl/pro_plus/control_table_592_present_input_voltage.md %}

### <a name="present-temperature"></a>**[Present Temperature(594)](#present-temperature594)**
{% include kr/dxl/pro_plus/control_table_594_present_temperature.md %}

# [조립 예시](#조립-예시)

## [옵션프레임 조립](#옵션프레임-조립)

![](/assets/images/platform/rh_p12_rn/rh-p12-rn_assembly.png)


# [참고자료](#참고자료)

## [커넥터 정보](#커넥터-정보)

|     항목     |                           RS-485                           |                                  외부포트                                  |
|:------------:|:----------------------------------------------------------:|:--------------------------------------------------------------------------:|
|   핀 번호    |        `1` GND<br>`2` VDD<br>`3` DATA+<br>`4` DATA-        | `1` GND<br>`2` VDD<br>`3` PORT 1<br>`4` PORT 2<br>`5` PORT 3<br>`6` PORT 4 |
|  다이어그램  |       ![](/assets/images/dxl/jst_b4beha_diagram.png)       |             ![](/assets/images/dxl/molex_5304706_diagram.png)              |
|    하우징    |                        [JST EHR-04]                        |    ![](/assets/images/dxl/molex_510210600.png)<br />[MOLEX 51021-0600]     |
|   PCB 헤더   | ![](/assets/images/dxl/jst_b4beha.png)<br />[JST B4B-EH-A] |    ![](/assets/images/dxl/molex_530470610.png)<br />[MOLEX 53047-0610]     |
| Crimp 터미널 |                    [JST SEH-001T-P0.6]                     |                             [MOLEX 50079-8100]                             |
|  Wire Gauge  |                           21 AWG                           |                                   21 AWG                                   |

[JST EHR-04]: http://www.jst-mfg.com/product/pdf/eng/eEH.pdf
[JST B4B-EH-A]: http://www.jst-mfg.com/product/pdf/eng/eEH.pdf
[JST SEH-001T-P0.6]: http://www.jst-mfg.com/product/pdf/eng/eEH.pdf
[MOLEX 51021-0600]: http://www.molex.com/molex/products/datasheet.jsp?part=active/0510210600_CRIMP_HOUSINGS.xml
[MOLEX 53047-0610]: http://www.molex.com/molex/products/datasheet.jsp?part=active/0530470610_PCB_HEADERS.xml
[MOLEX 50079-8100]: http://www.molex.com/molex/products/datasheet.jsp?part=active/0500798100_CRIMP_TERMINALS.xml

## [도면](#도면)
`다운로드` [RH-P12-RN(PDF).zip](http://www.robotis.com/service/download.php?no=740)  
`다운로드` [RH-P12-RN(STP).zip](http://www.robotis.com/service/download.php?no=741)

## [인증 획득](#인증-획득)
표기되지 않은 인증에 대해서는 별도 문의하시기 바랍니다.

### [FCC](#fcc)
{% include kr/dxl/fcc_class_b.md %}

{% include kr/dxl/common_link.md %}
