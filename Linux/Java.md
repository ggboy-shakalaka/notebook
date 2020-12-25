[toc]

# 关于Java的linux命令

## <span id="springboot_start">Springboot 启动命令<span>
``` shell
JAVA_HOME=
project_home=
project_name=

ps -ef|grep ${project_name}|grep -v grep|awk '{print$2}'|xargs -r kill -9

nohup \
    ${JAVA_HOME}/bin/java \
    -jar \
    ${project_home}/${project_name} \
    --spring.profiles.active=dev \
> /dev/null 2>&1

sleep 3

tailf ${project_home}/logs/info.log
```