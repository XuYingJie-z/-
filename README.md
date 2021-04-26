
# 爬虫资源

1. request 请求的基础用法见第二章，以下方代码为例，request使用post还是get方法，取决于网页的ajex请求类型，具体见视频
2. 获取响应数据使用什么方法也是要使用网页查看器
3. 注意这里的`response.json()`获取的响应数据，是可以在网页查看器里看到获得的相应数据是存储在列表还是字典里，是可以用列表和字典的方法提取出来的。同时json数据是可以用第三章的xpath进行解析的。


|   |   request方法   |         数据返回类型         |                                                                                                                               链接                                                                                                                               |
|:-:|:---------------:|:----------------------------:|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| 1 | requests.post() |        response.json()       | [百度翻译爬取](https://github.com/XuYingJie-z/Web_Crawler_tutorial/blob/master/%E7%AC%AC%E4%BA%8C%E7%AB%A0%EF%BC%9Arequests%E6%A8%A1%E5%9D%97%E5%9F%BA%E7%A1%80/03.requests%E5%AE%9E%E6%88%98%E4%B9%8B%E7%A0%B4%E8%A7%A3%E7%99%BE%E5%BA%A6%E7%BF%BB%E8%AF%91.py) |
| 2 |  requests.get() |        response.json()       | [豆瓣电影爬取](https://github.com/XuYingJie-z/Web_Crawler_tutorial/blob/master/%E7%AC%AC%E4%BA%8C%E7%AB%A0%EF%BC%9Arequests%E6%A8%A1%E5%9D%97%E5%9F%BA%E7%A1%80/04.requests%E5%AE%9E%E6%88%98%E4%B9%8B%E8%B1%86%E7%93%A3%E7%94%B5%E5%BD%B1%E7%88%AC%E5%8F%96.py) |
| 3 |  response.text  | response.text ！！这里没括号 |       [网页采集器](https://github.com/XuYingJie-z/Web_Crawler_tutorial/blob/master/%E7%AC%AC%E4%BA%8C%E7%AB%A0%EF%BC%9Arequests%E6%A8%A1%E5%9D%97%E5%9F%BA%E7%A1%80/02.requests%E5%AE%9E%E6%88%98%E4%B9%8B%E7%BD%91%E9%A1%B5%E9%87%87%E9%9B%86%E5%99%A8.py)      |



```python
    #1.指定url
    post_url = 'https://fanyi.baidu.com/sug'
    #2.进行UA伪装
    headers = {'User-Agent': 'Mozilla/5.0 (Macintosh; Intel Mac OS X 10_12_0) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/72.0.3626.121 Safari/537.36'}
  
    word = input('enter a word:')
    data = {
        'kw':word
    }
    #4.请求发送，！！！ 注意这里用的是post请求
    response = requests.post(url=post_url,data=data,headers=headers)
    #5.获取响应数据:json()方法返回的是obj（如果确认响应数据是json类型的，才可以使用json（））
    dic_obj = response.json()
    ```
