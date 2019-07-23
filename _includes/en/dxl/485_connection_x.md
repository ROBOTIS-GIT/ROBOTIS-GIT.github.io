## [Communication Circuit](#communication-circuit)
To control the Dynamixel actuators, the main controller needs to convert its UART signals to the half duplex type. The recommended circuit diagram for this is shown below.

### RS-485 Communication
![](/assets/images/dxl/x/x_series_485_circuit.jpg)

![](/assets/images/dxl/x/x_series_485_pin.png)

The power of Dynamixel is supplied via Pin1(-), Pin2(+).  
(The above circuit is built into Dynamixel-only controller.)  

{% include en/dxl/pinout_warning.md %}
