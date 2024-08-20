### 0x000.下载软件
[Node.js — Run JavaScript Everywhere](https://nodejs.org/en)
[Git - Downloads](https://git-scm.com/downloads)
### 0x001.操作步骤
在博客目录下右键选中git bash here打开bash窗口
使用npm 安装hexo
```
npm install -g hexo-cli                     //安装hexo
hexo init blog                              //初始化一个名为blog的项目
cd blog                                     //进入blog
hexo g                                      //编译构建
```
![QQ_1720593946698.png](https://cdn.nlark.com/yuque/0/2024/png/46258579/1720593963148-f6bc5303-d144-4670-89e9-f6f0d3d93c61.png#averageHue=%23060403&clientId=uec618a70-8443-4&from=paste&height=613&id=u41f17d85&originHeight=919&originWidth=809&originalType=binary&ratio=1.5&rotation=0&showTitle=false&size=102202&status=done&style=none&taskId=ub6b94aec-a240-4974-bec5-c5f8ded9b7b&title=&width=539.3333333333334)
测试博客新建博客文章
```
hexo new test_my_site                    //博客新建一个文章
hexo g                                   //构建
hexo s                                   //启动服务
之后就可以访问127.0.0.1:4000访问blog了
```
![QQ_1720594353623.png](https://cdn.nlark.com/yuque/0/2024/png/46258579/1720594383012-701fd825-f8fc-45e2-9b90-f3d3e955bd5f.png#averageHue=%23040302&clientId=uec618a70-8443-4&from=paste&height=335&id=u04fa2910&originHeight=503&originWidth=999&originalType=binary&ratio=1.5&rotation=0&showTitle=false&size=65236&status=done&style=none&taskId=u7c0ddc83-0cac-4f1c-94a0-65404429e6c&title=&width=666)
配置ssh
```
ssh-keygen -t rsa -C "邮件地址"
```
将id_rsa中的内容写入GitHub的SSH key
![QQ_1720595908707.png](https://cdn.nlark.com/yuque/0/2024/png/46258579/1720595914653-1d15b418-eac3-4e64-9ba9-d2d6745a2b28.png#averageHue=%23171614&clientId=uec618a70-8443-4&from=paste&height=490&id=ufeab7b0e&originHeight=735&originWidth=920&originalType=binary&ratio=1.5&rotation=0&showTitle=false&size=95040&status=done&style=none&taskId=u2f9aec4b-2e7f-473b-a967-246dd62cd76&title=&width=613.3333333333334)
测试能否链接上GitHub
```
ssh -T git@github.com # 注意邮箱地址不用改
```
![QQ_1720596071916.png](https://cdn.nlark.com/yuque/0/2024/png/46258579/1720596079698-1153ee3a-c105-4a75-b204-adb66e533b9e.png#averageHue=%23100e0c&clientId=uec618a70-8443-4&from=paste&height=105&id=u19caa59a&originHeight=158&originWidth=887&originalType=binary&ratio=1.5&rotation=0&showTitle=false&size=19394&status=done&style=none&taskId=u90a7daa7-a237-47f2-9810-0efac6b4267&title=&width=591.3333333333334)
```
npm install hexo-deployer-git --save
git config --global user.name "xxx"// 你的github用户名，非昵称
git config --global user.email  "xxx@qq.com"// 填写你的github注册邮箱
```
![QQ_1720596404382.png](https://cdn.nlark.com/yuque/0/2024/png/46258579/1720596413004-2dde8c07-d1dc-4ea1-95ed-e4481aac673c.png#averageHue=%23131210&clientId=uec618a70-8443-4&from=paste&height=316&id=u1f5b65bc&originHeight=474&originWidth=817&originalType=binary&ratio=1.5&rotation=0&showTitle=false&size=43455&status=done&style=none&taskId=uf17e3669-d768-4f6a-9f80-419a7be4f72&title=&width=544.6666666666666)
在github上新建一个存储库，命名为`github的用户名.github.io` 
编辑_config.yml文件，在最后改成这样 
```
deploy:
  type: git
  repository: git@github.com:xxx/xxx.github.io.git
  branch: main
```
![QQ_1720597175915.png](https://cdn.nlark.com/yuque/0/2024/png/46258579/1720597181121-7674cc6e-606b-41c1-b673-48092408df29.png#averageHue=%23020101&clientId=uec618a70-8443-4&from=paste&height=690&id=u47b3f001&originHeight=1035&originWidth=1343&originalType=binary&ratio=1.5&rotation=0&showTitle=false&size=138207&status=done&style=none&taskId=u6a9894b6-c773-427c-9c9c-ef16d13aca1&title=&width=895.3333333333334)
上传成功后登录xxx.github.io
```
hexo d
```
![QQ_1720597329892.png](https://cdn.nlark.com/yuque/0/2024/png/46258579/1720597336021-ad215d9d-c504-4aca-958f-acd1ae00c01a.png#averageHue=%230b0907&clientId=uec618a70-8443-4&from=paste&height=820&id=u01917f45&originHeight=1230&originWidth=1026&originalType=binary&ratio=1.5&rotation=0&showTitle=false&size=181966&status=done&style=none&taskId=ud1ffca91-fa18-48c8-9198-54ba15919d6&title=&width=684)
### 0x002.hexo介绍
```
hexo n "我的博客" == hexo new "我的博客" #新建文章
hexo new page "pageName" #新建页面
hexo g == hexo generate #生成
hexo s == hexo server #启动服务预览
hexo d == hexo deploy #部署

hexo server #Hexo会监视文件变动并自动更新，无须重启服务器
hexo server -s #静态模式
hexo server -p 5000 #更改端口
hexo server -i 192.168.1.1 #自定义 IP
hexo clean #清除缓存，若是网页正常情况下可以忽略这条命令
hexo version  #查看Hexo的版本
hexo generate #生成静态页面至public目录

hexo s -g #生成并本地预览
hexo d -g #生成并上传
```
```
+-- .deploy      #hexo deploy生成的文件
+-- node_modules  #npm组件
+-- public        #生成的静态网页文件
+--scaffolds      #模板
+-- source        #博客正文和其他源文件
|  +-- _posts    #我们自己写的文章以md结尾
+-- themes        #主题
+-- _config.yml  #全局配置文件
-- package.json  #定义了hexo所需要的各种模块
```
