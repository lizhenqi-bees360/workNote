### 工作笔记  2017.10.14
   
#### 传json格式数据给后台时，使用JSON.stringify()格式化  
#### vue-cli热更新失效  
  使用sudo n latest 更新node版本，然后使用sudo npm run dev启动
#### v-model
     v-model.lazy
     [参考链接](https://cn.vuejs.org/v2/guide/forms.html#修饰符 "Vue修饰符")
#### matlab启动桌面错误
     输入命令改变.matlab 权限即可 sudo chmod -R a+rw ~/.matlab  
#### 发布
      cd dist(发布的文件夹)  
      scp -r static bees@192.168.1.116:/home/bees/deploy/website  
      scp -r index.html bees@192.168.1.116:/home/bees/deploy/website   
      scp -r index.html static/ bees@192.168.1.116:/home/bees/servers/apache-tomcat-8.5.23/webapps/bees360-web  
#### matlab创建任何类型的结果矩阵
      [参考链接](https://cn.mathworks.com/help/matlab/apiref/mxcreatenumericarray.html "创建矩阵")
#### linux 修改文件拥有者
      chown [-R] 账号名称 文件或目录  
      chown [-R] 账号名称:用户组名称 文件或目录  
