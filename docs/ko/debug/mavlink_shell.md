# MAVLink 쉘

The MAVLink Shell is an _NSH console_ that can be accessed via MAVLink over serial (USB/Telemetry) or WiFi (UDP/TCP) links (in particular, on NuttX-based systems like: Pixhawk, Pixracer, etc.).

쉘은 명령 및 모듈을 실행하고 출력을 표시합니다.
While the shell cannot _directly_ display the output of modules that it does not start, it can do so indirectly using the `dmesg` command (`dmesg -f &` can be used to display the output of other modules and tasks running on the work queue).

:::tip
The [QGroundControl MAVLink Console](#qgroundcontrol) is the easiest way to access the console.
If the system does not start properly you should instead use the [System Console](../debug/system_console.md).
:::

## 쉘 열기

<a id="qgroundcontrol"></a>

### QGroundControl MAVLink Console

The easiest way to access shell is to use the [QGroundControl MAVLink Console](https://docs.qgroundcontrol.com/master/en/qgc-user-guide/analyze_view/mavlink_console.html) (see **Analyze View > Mavlink Console**).

### mavlink_shell.py

You can also access the shell in a terminal using the **mavlink_shell.py** script:

1. Shut down _QGroundControl_.

2. 종속성 설치:

   ```sh
   pip3 install --user pymavlink pyserial
   ```

3. 터미널(PX4-Autopilot 디렉토리)을 열고, 쉘을 시작합니다.

   ```sh
   # For serial port
   ./Tools/mavlink_shell.py /dev/ttyACM0
   ```

   ```sh
   # For Wifi connection
   ./Tools/mavlink_shell.py 0.0.0.0:14550
   ```

Use `mavlink_shell.py -h` to get a description of all available arguments.

## MAVLink 쉘 사용

For information see: [PX4 Consoles/Shells > Using Consoles/Shells](../debug/consoles.md#using_the_console).
