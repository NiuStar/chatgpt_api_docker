# chatgpt_api_docker

主要有以下几个接口：

## http://127.0.0.1:9090/mukj_chatgpt/login
参数如下：
```json
{
"email":"",
"password":""
}
```
## http://127.0.0.1:9090/mukj_chatgpt/talk
参数如下：
```json
{
"action":"next",
"puid":"XXXX",
"prompt":"你好",
"message_id":"uuid",
"parent_message_id":"parent_message_uuid",
"conversation_id":"conversation的id",
"model":"gpt4",
"plugins":["pluginid"]
}
```
## 部署docker-compose.yaml

```yaml
version: '3.3'
services:
    chatgpt-proxy:
        image: 24802117/chatgpt_api:latest
        container_name: chatgpt-api-v2
        ports:
            - '9090:9090'
        environment:
          api: http://xxxx/token?key=xxxx
          login_api: http://xxxx/login_token?key=xxxx
          3-5-ArkoseToken: http://xxxxx/token?key=xxx
          arkoselabs: 1
          PROXY: http://127.0.0.1:4000
```
