# WindowsJavaMock
To accelerate the development of mobile team
Mock介绍：http://wiremock.org/
第一步配置Java环境  地址：http://jingyan.baidu.com/article/e75aca85508d15142edac6b8.html
第二步：下载standalone.jar 地址：https://github.com/tomakehurst/wiremock 
第三步：写Bat工具（py等其他亦可），本文使用1.46版本，9991为端口号
@echo on
java -jar wiremock-1.46-standalone.jar --port 9991
@echo off
运行生成mappings和__files文件夹，mappings目录下写映射文件first-mapping.json
{
    "request": {
        "method": "GET",
        "url": "/api/login"
    },
    "response": {
        "status": 200,
        "bodyFileName": "login.json",
        "headers": {
            "Content-Type": "application/json",
            "Cache-Control": "max-age=86400"
        }
    }
}
_files目录下写请求结果login.json
{
    "working": "YES"
}
第四步浏览器访问：http://localhost:9991/api/login 获得请求结果
