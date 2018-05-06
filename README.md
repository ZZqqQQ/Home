# Home

## 简介

基于树莓派的智能家庭中控

## 实现

目前考虑使用树莓派做数据来源，有固定公网IP的服务器做数据中转，网页（微信）端显示

## 基础架构

### 树莓派架构

* 目前考虑使用Java来获取数据
* 树莓派自带温湿度传感器，具体程序（C语言）已经写好，并通过测试运行良好
* 需要商讨标准API来进行物联网硬件拓展
* 每个树莓派需要唯一识别码来给中转服务器做验证

### 服务器架构

* 目前考虑使用Node.JS做数据中转
* 使用MySQL缓存数据，不排除以后换成MongoDB

## 具体功能

### 显示天气（选）

若能获取到稳定易用的天气的API可考虑加入该功能
[中央天气预报API](https://github.com/jokermonn/-Api/blob/master/CenterWeather.md)

### 显示温湿度

树莓派相关检测程序已写好，只需稍作显示处理

### 智能硬件的添加

制定标准Json格式和通信标准后制定具体功能

### 智能硬件的显示

通过读取标准Json数据确定硬件类型和具体参数和功能

## 附

### 树莓派激活数据格式（待定）

```json
{
    "raspi_id" : "id",
    "raspi_name" : "name"
}
```

### 硬件通信标准API（待定）

```json
{
    "status" : "200",
    "devices" : [
        {
            "temp" : 26,
            "hum" : 85,
            "speaker" : [50,"pop"],
            "fan" : [3,"natural"],
            "light" : [5,"natural","#000000"]
            "..." : [...,...]
        }
    ]
}
```
