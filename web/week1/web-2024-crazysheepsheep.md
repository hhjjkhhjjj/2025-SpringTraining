# 1.BurpSuite的安装和初步使用
![](https://cdn.nlark.com/yuque/0/2025/png/54970229/1743088667759-b25f430c-0155-4379-9b51-501334716173.png)![](https://cdn.nlark.com/yuque/0/2025/png/54970229/1743088668513-c0080786-cfb8-4de5-bcaf-1895fcdf3416.png)

# 2.Hackerbar的安装![](https://cdn.nlark.com/yuque/0/2025/png/54970229/1743088764258-62779d3b-3243-4fa3-8c6b-d9645831e2b9.png)
![](https://cdn.nlark.com/yuque/0/2025/png/54970229/1743089679251-92c9451d-37f2-4d9f-b280-f666d2a5ba1d.png)

# 3.攻防题
![](https://cdn.nlark.com/yuque/0/2025/png/54970229/1743222332782-bec418b5-ea4c-462b-b9b0-a7664224b664.png)

# 4.AI搜索结果
```groovy
import hashlib

def find_md5_match():
    i = 0
    while True:
        data = str(i).encode('utf-8')
        md5_result = hashlib.md5(data).hexdigest()
        if md5_result[:6] == "19ca14":
            return data.decode('utf-8'), md5_result
        i += 1

value, md5_value = find_md5_match()
print(f"找到的值是: {value}")
print(f"其MD5加密结果是: {md5_value}")
```

# 5..php学习
和c语言很像，只是一些形式的改变

类比记忆：1.定义：$和int

   2.输出：echo和printf

   3.注释://与c相同

   4.结束标志：与c相同都是;

  	       5.定义类型：与c相同，例如有bool，数组，整型，浮点，字符串等等(可以调用var_dump查看类型）

   6.php的格式是<?php...?>

创建数组：`array("elemment one","element two"); `   (都有下标，例如：array[0]==》elemment one)

若在网站上运行出来是乱码，在前面加上`hender("Contont-Type: tent/html: charset=utf-8"）;`

还在持续学习ing（QAQ)



