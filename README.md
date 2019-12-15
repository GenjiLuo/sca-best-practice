# Microservice for NLP

本项目基于alibaba/sca-best-practice架框构建， 项目将Hanlp提供的多数接口进行了封装微服务化，以便Web端调用。

## 环境配置要求 
    * CentOS 7.0.x 或以上
    * 推荐 JDK 1.8以上
    * Maven

## Getting Started

基础环境配置结束后需要在shell命令行下执行 starup.sh ，依次启动nacos、sentinel-dashboard、sca-gateway、sca-hanlp。
##### 注意给startup.sh相应的执行权限,chmod +x startup.sh，默认监听IP和端口 127.0.0.1:9999

#### 调用方法
##### POST请求
     * 通过postman或curl等HTTP请求工具或类库，对接口进行调用。
     * http://127.0.0.1:9999/hanlp/v1/hanlp/segment
     * 请求头中，设置"Content-Type:x-www-form-urlencoded"，参数key为“sentence”，value为“你好，欢迎使用HanLP汉语处理包！”。
##### 示例：
     * >$ curl -H "Content-Type: x-www-form-urlencoded" -X POST --data "{"sentence":"你好，欢迎使用HanLP汉语处理包！"}"

## Control
#### 访问控制器
     * ## 以下为微服务对应的请求入口/接口清单,
     ** sca-best-practice/sca-hanlp/src/main/java/com/acgnfuns/controller/HanlpController.java
     
     * ## 以下为微服务具体业务实现
     ** sca-best-practice/sca-hanlp/src/main/java/com/acgnfuns/service/HanlpService.java
     
## Links

* [HanLP官方](https://github.com/hankcs/HanLP)
* [SCA Best Practice](https://github.com/alibaba/sca-best-practice)

## Authors

* **sppsun** - *Initial work* - [sppsun](https://github.com/sppsun)

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details
