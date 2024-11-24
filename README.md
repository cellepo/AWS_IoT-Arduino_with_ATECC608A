# AWS_IoT-Arduino_WiFi_ATECC608A
:chart_with_upwards_trend: &nbsp;_Persist arbitrary data from [Arduino](https://www.arduino.cc/), to Cloud of your chosing:_<br>
&nbsp;&nbsp;&nbsp;&nbsp; :money_with_wings: &nbsp;&nbsp;_No proprietary limit on space, bandwidth, history..._

:1st_place_medal: Please [Patronize](https://store.arduino.cc/) & [Donate to Arduino](https://www.arduino.cc/en/donate/) :blue_heart: :<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Its hardware designs/manufacturing, and softare are **_open-source_**!

## Summary
<ins>_**Polls &amp; Publishes data**</ins> from..._
### Hardware Requirements
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;_**[Arduino](https://support.arduino.cc/hc/en-us/articles/4407129094546-Boards-and-shields-with-wireless-connectivity)** microcontroller, having:_
* **`WiFi`** capability
* `ATECC608A` [cryptographic] capability <sub>  creates `X.509` Certificate for AWS authentication</sub>
  
... **_&lt;- <ins>To / From</ins> ->_**

### Cloud Requirements
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;_**[AWS IoT](https://aws.amazon.com/iot/?nc2=h_ql_prod_it_iot)**_
* _using [MQTT](https://aws.amazon.com/what-is/mqtt/) protocol_

## Setup
1. If using [Arduino IDE](https://www.arduino.cc/en/software):<br>
   Set root path of this local repo to `Arduino IDE > Settings > Sketchbook location`
   
2. Install libraries [all by `Arduino`], & (if prompted for) their dependencies:
   * `ArduinoBearSSL`<br>
   * `ArduinoECCX08`<br>
   * `ArduinoMqttClient`<br>
   * `WifiNINA`
     
3. Copy templates to local files & Fill:<br>
  3.1. Copy `AWS_IoT_WiFi/arduino.secrets.h.template` -> new `AWS_IoT_WiFi/arduino.secrets.h`<br>
  &nbsp;&nbsp;3.1.1. Fill non-template (including [with values](https://docs.arduino.cc/tutorials/opta/getting-started-with-aws-iot-core/#connecting-your-device-to-aws-iot-core) subsequently from _Usage_ below)<br>
		<br>
  3.2. Copy `AWS_IoT_WiFi/properties.local.h.template` -> new `AWS_IoT_WiFi/properties.local.h`<br>
  &nbsp;&nbsp;3.2.1. Fill non-template (including [with values](https://docs.arduino.cc/tutorials/opta/getting-started-with-aws-iot-core/#connecting-your-device-to-aws-iot-core) subsequently from _Usage_ below)

## Usage
Follow [https://docs.arduino.cc/tutorials/opta/getting-started-with-aws-iot-core](https://docs.arduino.cc/tutorials/opta/getting-started-with-aws-iot-core):
  * Ignore references to `Opta` (if not using an `Arduino Opta` board):  Adapt as appropriate with your `Arduino` board instead
  * regardless of your environment, Start following those steps no later than [Generating a Certificate Signing Request](https://docs.arduino.cc/tutorials/opta/getting-started-with-aws-iot-core/#generating-a-certificate-signing-request)
  
## Development
### Roadmap
* Update main `.ino` directory name
* Cleanup code (beyond minimal implementation of 'Arduino Cloud_Examples > AWS IoT > AWS_IoT_WiFi')
* Refactor `poll()` & `publishMessage()` into an interface/implementation, called from `loop()`
* Make an interface implementation for capturing temperature data (for Arduino having LSM6DSOXTR IMU sensor)

