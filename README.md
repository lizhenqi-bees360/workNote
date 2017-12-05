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
https://help.github.com/articles/changing-a-remote-s-url/#platform-linux  
#### 请输入一个提交信息以解释此合并的必要性，尤其是将一个更新后的上游分支 # 合并到主题分支 解决方法
   http://9i9icenter.com/huanqiuNews/5854034a128fe1006b5ff19e
#### ubuntu解决声音问题 pavucontrol
   https://lms.im/os/no-sound-solution-ubuntu-16-04.html  
#### 点云循环显示，可能优化的一个方面  

```
//分开循环更快  
	//x: 200-400 , y: 100-250
	for(var i=0; i<2000; i++){
		face['x'] = Math.random()*200 +200;
		face['y'] = Math.random()*150 +100;
		$myCanvas.drawArc(face);
	}
	//x: 500-700 , y: 100-250
	for(var i=0; i<2000; i++){
		face['x'] = Math.random()*200 +500;
		face['y'] = Math.random()*150 +100;
		$myCanvas.drawArc(face);
	}
	//x: 200-700 , y: 250-400
	for(var i=0; i<4000; i++){
		face['x'] = Math.random()*500 +200;
		face['y'] = Math.random()*150 +250;
		$myCanvas.drawArc(face);
	}
```
#### jcanvas 清除画布
https://github.com/caleb531/jcanvas-docs/wiki/Canvas-Clear-canvas-%E6%B8%85%E7%A9%BA%E7%94%BB%E5%B8%83%EF%BC%88%E6%96%B0%EF%BC%89
#### int 字节流格式化

```
var uint8array = new TextEncoder("utf-8").encode("¢");
var string = new TextDecoder("utf-8").decode(uint8array);
```


