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

- /dev/ttyS0 :  Cong
- /dev/ttyS0 là các chân 14 , 15(TX,RX) trên header của raspberry.
Để dùng Serial này ta phải config system của raspberry bằng
 ```sudo raspi-config``` sau đó vào ```5. Interfacing Options``` -> ```P6. Serial``` -> ```OK``` và reboot Raspberry để dùng cổng UART trên pin 14,15.

 Sau đó ta cần disable Serial Console:

 ```sudo nano /boot/cmdline.txt``` -> remote ```console=serial0,115200``` -> ```sudo reboot```



- /dev/ttyUSB0 là cổng USB của raspberry