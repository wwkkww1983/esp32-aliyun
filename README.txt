1����¡��esp_aliyun�ֿ�:
		GitHub��ȡ�� git clone --recursive https://github.com/espressif/esp-aliyun.git
		������ȡ�� git clone --recursive https://gitee.com/xuhongv/esp-aliyun
		����esp-idf��

2����examples/solutions/smart_lightĿ¼����esp32+���ڣ�
		make chip=esp32 defconfig
		make menuconfig

3���� USB �����Ӻ� ESP �豸�� PC���б������أ�
		make all
		make flash

4���ҵ� single_mfg_config.csv �ļ���д��Ԫ�������
		ע����ַ��https://iot.aligenie.com/home

5����single_mfg_config.csv����bin�ļ���
		$IDF_PATH/components/nvs_flash/nvs_partition_generator/nvs_partition_gen.py --input single_mfg_config.csv --output my_single_mfg.bin --size 0x4000

6����single_mfg_config.csv������¼����ļ���ȥ��
		$IDF_PATH/components/esptool_py/esptool/esptool.py write_flash 0x210000 my_single_mfg.bin





