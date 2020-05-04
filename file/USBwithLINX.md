VISA Find Resource

mapping  /dev/tty* to VISA resource name in file ```/srv/chroot/labview/usr/local/vxipnp/linux/NIvisa/visaconf.ini```

```
[VISA-CONFIG]
UnloadPassports=0
MaxNumResources=64
NumSystemSems=128
NumProcessSems=512
SharedMemSize=262144
ShowRegisteredDevOnly=1

[REMOTE-ACCESS]
Address0="*"
AccessLevel0=1
NumEntries=1

[ALIASES]
NumAliases=4

[ASRL-RSRC-ALIAS]
Name0="ASRL1::INSTR"
Enabled0=1
Static0=0
SystemName0="/dev/ttyS0"
BaudRate0=9600
Parity0=0
StopBits0=10
DataBits0=8
FlowCtrl0=0
Name1="ASRL2::INSTR"
Enabled1=1
Static1=0
SystemName1="/dev/ttyACM0"
BaudRate1=9600
Parity1=0
StopBits1=10
DataBits1=8
FlowCtrl1=0
Name2="ASRL3::INSTR"
Enabled2=1
Static2=0
SystemName2="/dev/ttyAMA0"
BaudRate2=9600
Parity2=0
StopBits2=10
DataBits2=8
FlowCtrl2=0
Name3="ASRL4::INSTR"
Enabled3=1
Static3=0
SystemName3="/dev/ttyACM1"
BaudRate3=9600
Parity3=0
StopBits3=10
DataBits3=8
FlowCtrl3=0
Name4="ASRL5::INSTR"
Enabled4=1
Static4=0
SystemName4="/dev/ttyUSB0"
BaudRate4=9600
Parity4=0
StopBits4=10
DataBits4=8
FlowCtrl4=0
NumOfResources=5


```

```
[VISA-CONFIG]
UnloadPassports=0
MaxNumResources=64
NumSystemSems=128
NumProcessSems=512
SharedMemSize=262144
ShowRegisteredDevOnly=1

[REMOTE-ACCESS]
Address0="*"
AccessLevel0=1
NumEntries=1

[ALIASES]
Alias0="'USB4','ASRL23::INSTR'"
Alias1="'USB1','ASRL25::INSTR'"
Alias2="'USB2','ASRL26::INSTR'"
Alias3="'USB3','ASRL27::INSTR'"
Alias4="'USB485','ASRL50::INSTR'"
Alias5="'USBMulti','ASRL51::INSTR'"
Alias6="'/dev/ttyUSB0','ASRL8::INSTR'"
NumAliases=7

[ASRL-RSRC-ALIAS]
Name0="ASRL1::INSTR"
Enabled0=1
Static0=0
SystemName0="/dev/ttyS0"
BaudRate0=9600
Parity0=0
StopBits0=10
DataBits0=8
FlowCtrl0=0
Name1="ASRL2::INSTR"
Enabled1=1
Static1=0
SystemName1="/dev/ttyAMA0"
BaudRate1=9600
Parity1=0
StopBits1=10
DataBits1=8
FlowCtrl1=0
Name2="ASRL23::INSTR"
Enabled2=1
Static2=0
SystemName2="/dev/ttyUSB_P4"
BaudRate2=9600
Parity2=0
StopBits2=10
DataBits2=8
FlowCtrl2=0
Name3="ASRL4::INSTR"
Enabled3=1
Static3=0
SystemName3="/dev/ttyACM1"
BaudRate3=9600
Parity3=0
StopBits3=10
DataBits3=8
FlowCtrl3=0
Name4="ASRL25::INSTR"
Enabled4=1
Static4=0
SystemName4="/dev/ttyUSB_P1"
BaudRate4=9600
Parity4=0
StopBits4=10
DataBits4=8
FlowCtrl4=0
Name5="ASRL26::INSTR"
Enabled5=1
Static5=0
SystemName5="/dev/ttyUSB_P2"
BaudRate5=9600
Parity5=0
StopBits5=10
DataBits5=8
FlowCtrl5=0
Name6="ASRL27::INSTR"
Enabled6=1
Static6=0
SystemName6="/dev/ttyUSB_P3"
BaudRate6=9600
Parity6=0
StopBits6=10
DataBits6=8
FlowCtrl6=0
Name7="ASRL8::INSTR"
Enabled7=1
Static7=0
SystemName7="/dev/ttyUSB0"
BaudRate7=9600
Parity7=0
StopBits7=10
DataBits7=8
FlowCtrl7=0
Name7="ASRL8::INSTR"
Enabled7=1
Static7=0
SystemName7="/dev/ttyUSB0"
BaudRate7=9600
Parity7=0
StopBits7=10
DataBits7=8
FlowCtrl7=0
Name8="ASRL50::INSTR"
Enabled8=1
Static8=0
SystemName8="/dev/USB485"
BaudRate8=9600
Parity8=0
StopBits8=10
DataBits8=8
FlowCtrl8=0
Name9="ASRL51::INSTR"
Enabled9=1
Static9=0
SystemName9="/dev/USBMultiMode"
BaudRate9=9600
Parity9=0
StopBits9=10
DataBits9=8
FlowCtrl9=0
NumOfResources=10
```

- /dev/ttyS0 :  Cong
- /dev/ttyS0 là các chân 14 , 15(TX,RX) trên header của raspberry.
Để dùng Serial này ta phải config system của raspberry bằng
 ```sudo raspi-config``` sau đó vào ```5. Interfacing Options``` -> ```P6. Serial``` -> ```OK``` và reboot Raspberry để dùng cổng UART trên pin 14,15.

 Sau đó ta cần disable Serial Console:

 ```sudo nano /boot/cmdline.txt``` -> remote ```console=serial0,115200``` -> ```sudo reboot```



- /dev/ttyUSB0 là cổng USB của raspberry