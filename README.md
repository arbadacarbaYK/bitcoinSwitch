<img width="600" src="https://user-images.githubusercontent.com/33088785/166832680-600ed270-cbc9-4749-82f1-c1853b242329.png"><img width="600" src="https://user-images.githubusercontent.com/33088785/166829474-a28ca2b7-dd3e-46d4-89d3-8a10bf1d3fad.png">

# Clicky, the Bitcoin Switch

👉 An absolutely incredible <a href="https://ereignishorizont.xyz/bitcoinswitch/en/">bitcoinSwitch guide</a> by [Axel](https://github.com/AxelHamburch/) 👈

Also check out our <a href="https://twitter.com/arcbtc/status/1585627498510831616">video tutorial</a>.


✅ $8 worth parts / 15min setup

✅ Websockets for blazingly fast turning on the things

✅ Web-installer/config for easy setup

✅ Support for MULTIPLE GPIOS/LNURLs (!)


# Flash and configure via webinstaller https://bitcoinswitch.lnbits.com/

<img src="https://github.com/lnbits/bitcoinswitch/assets/63317640/35936b5d-d337-4dcb-8967-5f33d087b6d7" alt="switch_front" width="200">
<img src="https://github.com/lnbits/bitcoinswitch/assets/63317640/ce702a01-a315-4a0c-a86a-c69fe6a79264" alt="switch_back" width="200">


### Things you can turn on with a switch

There is a broad range of things from lamps, to candy-, claw or even arcade machines that can be turned on by a lightning payment with Clicky. 
Have a look at the [LNbits shop](https://shop.lnbits.com/product-category/hardware/fun-things) what we did or check the [LNbits wiki](https://github.com/lnbits/lnbits/wiki/Tooling-&-Building-with-LNbits) on how to build those yourself.


### What you need
- esp32 dev kit
- High level relais
- Female to male and male to male cables
- Data cable
- Optional: a case
- Desktop PC
- LNbits LNURLdevice Extension
- Something to turn on
  

   <table>
  <tr>
    <th><img src="https://user-images.githubusercontent.com/33088785/204107016-bc9473e0-2843-4873-af71-cd934e07f444.gif" alt="Snow" style="width:80%"></th>
    <th><img src="https://user-images.githubusercontent.com/33088785/204107029-cc4ad95b-b130-4b48-9091-86d7be7d4f16.gif" alt="Forest" style="width:80%"></th>
    <th><img src="https://user-images.githubusercontent.com/33088785/204107037-870571f8-b860-4019-93d4-bbdbeaf1091f.gif" alt="Mountains" style="width:80%"></th>
    <th><img src="https://user-images.githubusercontent.com/33088785/204107044-b8a7d94f-6908-40dd-bb82-974e08f077f4.gif" alt="Mountains" style="width:80%"></th>
  </tr>
</table>

Once flashed, press GPIO4 in few seconds of ESP32 booting up to be able to config.


Got questions ? Join us <a href="https://t.me/lnbits">t.me/lnbits</a>, <a href="https://t.me/makerbits">t.me/makerbits</a>


## Complicated install instructions not using browser flashing

- Install <a href="https://www.arduino.cc/en/software">Arduino IDE 1.8.19</a>
- Install ESP32 boards, using <a href="https://docs.espressif.com/projects/arduino-esp32/en/latest/installing.html#installing-using-boards-manager">boards manager</a>
![image](https://user-images.githubusercontent.com/33088785/161862832-1269a12e-16ce-427c-9a92-df3ee573a1fb.png)

- Download this repo
- Copy these <a href="libraries">libraries</a> into your Arduino install "libraries" folder
- Open this <a href="bitcoinSwitch.ino">bitcoinSwitch.ino</a> file in the Arduino IDE
- Select the correct ESP32 board from tools>board
- Upload to device

![trigger](https://user-images.githubusercontent.com/33088785/166829947-d0194b32-19fc-4a16-83d3-dc6f9af9337c.gif)


### Development
build with arduino-cli
```console
sh build.sh
```
build webinstaller, fetch main assets from lnbits.github.io
```console
sh build-installer.sh
```
start preview
```console
cd installer
http-server -p 8080
```

### arduino-cli
compiling
```console
arduino-cli compile --build-path build --fqbn esp32:esp32:esp32 bitcoinSwitch
```
monitoring
```console
arduino-cli monitor -p /dev/ttyUSB1 -c baudrate=115200
```
uploading
```console
arduino-cli upload --fqbn esp32:esp32:esp32 --input-dir build -p /dev/ttyUSB1
```
