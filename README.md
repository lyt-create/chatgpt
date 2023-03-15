# chatgpt
chatgpt国内https接口，直接请求即可

chatGPT开放接口使用说明-更新至gpt-3.5-turbo模型
更新至gpt-3.5-turbo模型

 

1.请求地址： https://lytcreate.com/api/chat/

2.请求方式: POST

3.body格式：json

4.body请求体：

{
    "token": "个人中心获取 -- 非openai的key",
    "question": "请求的问题"
}
说明：

token获取方式：访问首页(https://lytcreate.com)，注册后登陆，访问后台，进入个人信息查看 token

5.响应体格式：json

6.响应体：

复制代码
{
            "code": 200/403/405,
            "question": "提交的问题",
            "answer": "chatGPT的回答",
            "message": "响应提示信息",
            "api_num": 999(剩余可请求次数)
        }
复制代码
7.请求实例(python)

复制代码
    import requests
    url = "https://lytcreate.com/api/chat/"
    body = {
        "token": "xxxxxxxxx-token",
        "question": "太阳从哪边升起？"
    }
    res = requests.post(url, json=body)
    print(json.loads(res.content))
复制代码
 

有任何疑问请加入QQ交流群：733690997

特别说明： 2023.03.04更新

如果需要有上下文语境，请把之前问的问题用user区分作为question传过来即可，例如question= ”user: 你好.user:你是chatGPT吗？user:写个冒泡排序.“，举例：

question1 = "你好！"

question2: "今天天气怎么样？"

那么第二次提交带user和问题即可，请求体里面的question就是：

question = " user:你好！user:今天天气怎么样？"

这样获取的答案就是支持上下文语境了哈～

