# 莱因特 t68m ARMBIAN
## 设备树参考来源
``` bash
  https://github.com/coolsnowwolf/lede
  https://github.com/amazingfate/armbian-h68k-images
  # 感谢LEAN提供支持协助,感谢68k的armbian git库
  # 目前所有可见接口均可使用,hdmi,usb2.0和usb3.0,4个网口等都工作正常
```
## 关于2个1Gb网口mac地址不能保存的问题
### 由于厂家那边没有用RKDevInfoWriteTool写码工具对设备的mac地址和sn进行写码，需要使用的话写入2个千兆网口的mac地址即可
### 自己手动在系统层把mac地址写固定也是可以的

## 首次开机比较慢，系统需要对硬盘进行resize和初始配置，图像界面需要使用性能更好的tf卡，或者直接写入emmc

## t68m 板级配置文件
``` bash
config/boards/lyt-t68m.conf
```

## t68m 内核config
``` bash
config/kernel/linux-rk35xx-legacy.config
```

## t68m补丁,没有rk35xx-5.10文件夹的话可以手动创建一个,使上层的link(rk35xx-legacy)生效
``` bash
patch/kernel/archive/rk35xx-5.10/board-add-t68m-makefile.patch
patch/kernel/archive/rk35xx-5.10/board-dts-add-lyt-t68m.patch
```
#### 由于armbian rockchip内核里面的makefile更新很活跃,直接给追加到前面了，(不使用字母排序接入补丁)不用考虑后面由于makefile变动导致patch失败

## 设备树文件
arch/arm64/boot/dts/rockchip/rk3568-lyt-t68m.dts
设备树文件不用管，已经集成到补丁了

#### armbian构建套件地址 https://github.com/armbian/build.git
#### 把对应的文件拷贝到armbian build 目录，然后执行./compile.sh
### 选择 lyt-t68m
