#莱因特 t68m ARMBIAN

## t68m 板级配置文件
``` bash
config/boards/lyt-t68m.conf
```

##t68m 内核config
``` bash
config/kernel/linux-rk35xx-legacy.config
```

##t68m补丁
``` bash
patch/kernel/archive/rk35xx-5.10/board-add-t68m-makefile.patch
patch/kernel/archive/rk35xx-5.10/board-dts-add-lyt-t68m.patch
```

## 修复软链
``` bash
patch/kernel/rk35xx-legacy -> patch/kernel/archive/rk35xx-5.10
```

##设备树文件
arch/arm64/boot/dts/rockchip/rk3568-lyt-t68m.dts
设备树文件不用管，已经集成到补丁了

https://github.com/armbian/build.git
把对应的文件拷贝到armbian build 目录，然后执行./compile.sh
选择 lyt-t68m
