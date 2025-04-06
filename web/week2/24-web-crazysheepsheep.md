week2

# 1.![](https://cdn.nlark.com/yuque/0/2025/png/54970229/1743346827085-813dcb68-57c2-42a0-b40e-0e468eca1c5b.png)
按照给的提示把get和post传参直接完成了，然后说有彩蛋，利用`python dirsearch.py -h url`找到彩蛋，有点没看懂这个彩蛋![](https://cdn.nlark.com/yuque/0/2025/png/54970229/1743346967989-1a90acdb-54ef-4ef1-8d99-4be50f715548.png)

# 2.第二题
![](https://cdn.nlark.com/yuque/0/2025/png/54970229/1743347739182-8d669378-f6d9-412c-b6e8-0fe5782a04ab.png)

先根据提示，把user agent改成wllm，但他给了个地址，有点不知道怎么处理，然后输入这个地址，怎么跑中国联通去了<哭笑>

![](https://cdn.nlark.com/yuque/0/2025/png/54970229/1743347987091-979acc1a-bc30-4a0b-9860-18b8d57ba240.png)

看了一下各位大佬的答题,然后试一下bp抓包

![](https://cdn.nlark.com/yuque/0/2025/png/54970229/1743348938152-b3389102-fed0-47de-88c0-ef9c65e62284.png)

然后修改，增添`X-Forwarded-For:127.0.0.1 `==》还没搞懂啥意思![](https://cdn.nlark.com/yuque/0/2025/png/54970229/1743503439976-d597c1e0-b866-404d-914f-89d2fcbf96ef.png)

最后就找到flag了

# 3.第三题
![](https://cdn.nlark.com/yuque/0/2025/png/54970229/1743504341700-e3b2192a-2087-4e58-9d8a-b9e0011f6d6b.png)

几个意思？看得我蒙了一下![](https://cdn.nlark.com/yuque/0/2025/png/54970229/1743519775264-5326b59a-76d6-43e6-a245-b6dc7175f807.png)

![](https://cdn.nlark.com/yuque/0/2025/png/54970229/1743519935762-2b7ae3d9-a1e9-4355-bd39-c7124660d119.png)

![](https://cdn.nlark.com/yuque/0/2025/png/54970229/1743519944694-f32c16b1-4747-4cb6-8ac2-9f27e8fc6039.png)

时间是2023的，点击关于，去GitHub中找他之前的目录，然后找到flag文件，再去寻找到flag答案，最后要修改他的要求成` NSSCTF{g1thub_c0mmit_1s_s0_us3ful}`

# 第四题
用dirsearch扫描文件

![](https://cdn.nlark.com/yuque/0/2025/png/54970229/1743860569062-20e15339-ff6e-475f-b233-929f0ddf95b3.png)

加入[/phpinfo.php](http://node4.anna.nssctf.cn:28064/phpinfo.php)查询找到flag就完成了

![](https://cdn.nlark.com/yuque/0/2025/png/54970229/1743860576402-93462129-da3f-40cd-afe9-e284db5f8b31.png)

# 第五题
![](https://cdn.nlark.com/yuque/0/2025/png/54970229/1743930620312-3b34afa5-14a9-4256-aae2-c5e8c406a73a.png)

根据eval及get传参，能够知道eval可以执行代码命令，那我们可以直接去查询url的根目录`?url=system("ls /");`(一定要加冒号，刚刚死活运行不出来，发现少了冒号）//哭笑

然后得到` bin boot dev etc flllllaaaaaaggggggg home lib lib64 media mnt opt proc root run sbin srv sys tmp usr var  `那我们可以用cat去连接文件（cat+文件命令是能够去显示或连接文件的作用）`/?url=system("cat /flllllaaaaaaggggggg"); `

![](https://cdn.nlark.com/yuque/0/2025/png/54970229/1743930938421-8b630a85-6242-466d-aa54-0f721c37b510.png)

最后得到flag

# 第六题
![](https://cdn.nlark.com/yuque/0/2025/png/54970229/1743931560747-2065422a-52de-41e7-9df9-f57fadd9aac2.png)

上csdn搜奇妙字符串，也就是万能密码，那就直接上万能密码 ` ffifdyop  `

![](https://cdn.nlark.com/yuque/0/2025/png/54970229/1743932804525-36c055df-7cc7-4f26-a168-4bfae186c6f1.png)

f12查看器发现是md5（）比较类型（ 经过 md5 加密后 276f722736c95d99e921722cf9ed621c  
再转换为字符串：'or’6<乱码> 即 'or’66�]��!r,��b  ）

再get传入![](https://cdn.nlark.com/yuque/0/2025/png/54970229/1743933866540-2b0b596e-6aa7-45d0-96b6-e35d835b35c7.png)

//md5加密OE开头`QNKCDZO 240610708 byGcY sonZ7y aabg7XSs aabC9RqS s878926199a s155964671a s214587387a s1091221200a `

![](https://cdn.nlark.com/yuque/0/2025/png/54970229/1743933891254-8cf8e630-2bc5-41df-8fa3-7a8404eedc4d.png)

发现又是一个md5比较类型，但和上一个不一样，这个传入数组会报错，所以可以构造payload`wqh[]=1&dsy[]=2 `传出是null=null型，用post传参，输入代码，得到flag

![](https://cdn.nlark.com/yuque/0/2025/png/54970229/1743934261482-345e4e7a-9f36-430e-988c-f32c4a442049.png)

# 第七题
![](https://cdn.nlark.com/yuque/0/2025/png/54970229/1743934361202-f2a14fa5-f92a-40c1-a490-41ec8f018281.png)

似曾相识，依然用万能密码进入

![](https://cdn.nlark.com/yuque/0/2025/png/54970229/1743934742379-4f53dcbf-fb73-4e18-9106-7c074622041a.png)

此时我们需要满足a不等于b，但md5后的大小要相等，构造` ?a[]=1&b[]=2  `

![](https://cdn.nlark.com/yuque/0/2025/png/54970229/1743934825923-952b506d-8c8c-4c05-a339-e0d71b6383cb.png)

这要求两个的内容不能相等，但强比较后要相等` param1[]=1&param2[]=2`

![](https://cdn.nlark.com/yuque/0/2025/png/54970229/1743935014952-edf29ffe-9c35-4496-a699-2449b3090bd1.png)

最后得到flag

