## Hunters末期考核机械臂
#### 材料列表
单片机: STM32F407ZGT6  
步进电机: MS42CG * 4  
电机驱动模块: D36AX1 * 2  
舵机: 众灵科技ZP10S * 1  
电源模块: HJ-DC12 * 1  
摄像头: 立创庐山派K230 * 1

#### 蓝牙烧录
打开 STM32_Programmer_CLI.exe(修改为自己的路径):  
`$cli = (Get-Command STM32_Programmer_CLI.exe -ErrorAction SilentlyContinue).Source
if (-not $cli) {
    $cli = Get-ChildItem 'D:\Program Files\ST' -Recurse -Filter STM32_Programmer_CLI.exe -ErrorAction SilentlyContinue |
        Select-Object -First 1 -ExpandProperty FullName
}
$cli`

测试传出串口(视情况修改COM串口):  
`& $cli -c port=COM5 br=9600 P=EVEN`

烧录命令:  
`& $cli -c port=COM5 br=9600 P=EVEN -w ".\build\Debug\roboticArm.elf" -v`