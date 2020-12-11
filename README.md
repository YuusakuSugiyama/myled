# Name

led_driver

---

 # Featuers
 
ロボットシステム学の講義内で作成した[デバイスドライバ](https://github.com/ryuichiueda/robosys_device_drivers/blob/master/myled.c)を元に改良を加えて以下のように動作するようにしました。  
・LEDを3個使用し入力に応じて、二進数の0～7までの数値をLEDの点灯の切り替えにより表現します。  

---

# Demo

youtubeに公開したデモムービーは[こちら](https://youtu.be/1kebJaBuN5U)  

---

# Requirement & tool

## Requirement
・Raspberry Pi 4 Model B  
・Ubuntu 20.04.1 LTS  
## tool
・ブレットボード  
・LED(3個)  
・100Ω抵抗(3個）  
・ジャンパー線　オス-メス(6本)  

---

# Build
```sh
$ git clone https://github.com/YuusakuSugiyama/myled.git
$ cd ~/myled
$ make
$ sudo insmod myled.ko
$ sudo chmod 666 /dev/myled0
```
## Circuit
・GPIO 23/24/25が出力のピンなので各ピンからジャンパー線を伸ばし、ブレットボード上でLEDと接続してください。  
・GNDは任意のGNDピンに接続してください。  

---

# Run

```sh
$ echo 0 > /dev/myled0
```

echo 0　の0を0～7までの表示させたい任意の数字に変更して実行してください。

---

# End

```sh
$ sudo rmmod mydriver
$ make clean
```

---

# Author
[YuusakuSugiyama](https://github.com/YuusakuSugiyama)  
ベースのプログラム開発者 : [Ryuichi Ueda](https://github.com/ryuichiueda)  

## 一緒に考えた人
Tatsuki Saito  

---

# License
[GNU General Public License v3.0](https://github.com/zjzj-zz/robosys2020_devicedriver/blob/main/COPYING) 
