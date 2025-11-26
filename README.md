# i2c_master_nicolle_style
效仿Jean P. Nicolle风格的代码实现，用在mpu6050上实测可以用，但是不建议用到工业产品上。哈哈哈，好多瑕疵，大佬难以望其项背！

- 刻意保留单 always 块 + 计数器核心结构，向 fpga4fun 创始人 Jean P. Nicolle 致敬
- 支持任意长度读写 + Repeated Start + ACK 错误检测与恢复
- 基于相位累加器（DDS）实现精准 SCL，1/4 相位点精确控制 SDA 建立/保持时间
- 仿真/综合分离（`VSC_SIM` 宏）
- 已在 ZYNQ7020 开发板实测跑通 400kHz，MPU6050正确通讯

后续考虑看看要不要做一个三段式工业规范版本（i2c_master_industrial），也是基于这种风格。
