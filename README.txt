1、克隆下esp_aliyun仓库:
		GitHub拉取： git clone --recursive https://github.com/espressif/esp-aliyun.git
		码云拉取： git clone --recursive https://gitee.com/xuhongv/esp-aliyun
		放置esp-idf下

2、到examples/solutions/smart_light目录配置esp32+串口：
		make chip=esp32 defconfig
		make menuconfig

3、将 USB 线连接好 ESP 设备和 PC进行编译下载：
		make all
		make flash

4、找到 single_mfg_config.csv 文件填写三元组参数：
		注册网址：https://iot.aligenie.com/home

5、到single_mfg_config.csv生成bin文件：
		$IDF_PATH/components/nvs_flash/nvs_partition_generator/nvs_partition_gen.py --input single_mfg_config.csv --output my_single_mfg.bin --size 0x4000

6、到single_mfg_config.csv单独烧录这个文件进去：
		$IDF_PATH/components/esptool_py/esptool/esptool.py write_flash 0x210000 my_single_mfg.bin





