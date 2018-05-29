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
https://stackoverflow.com/questions/8936984/uint8array-to-string-in-javascript  

#### 整数转化为对应进制的字符串
```
Number.toString(n)
Number.toString(2)
Number.toString(8)
Number.toString(16)
```
#### 对数组操作元素,增加和刪除
	1. 删除一个元素 Array.splice(index,1)
	2. 增加一个元素 Array.splice(index,0,value)  0代表不替换其他的
	3. 替换一个元素 Array.splice(index,1,value)
#### matlab .mat 转 csv
```
csvwrite('points.csv', house3Dinfo.modelInfo.iniSFMAndPMVS.densePC.Location)
```
#### 使用ranjian电脑CPU
```
ssh -X 192.168.1.152
locate matlab
sudo /usr/local/MATLAB/R2017a/bin/matlab
```
#### 写接口文档时的命名规范？？？

#### 信用卡格式
```
cards = [
    {
      type: 'amex',
      pattern: /^3[47]/,
      format: /(\d{1,4})(\d{1,6})?(\d{1,5})?/,
      length: [15],
      cvcLength: [4],
      luhn: true
    }, {
      type: 'dankort',
      pattern: /^5019/,
      format: defaultFormat,
      length: [16],
      cvcLength: [3],
      luhn: true
    }, {
      type: 'hipercard',
      pattern: /^(384100|384140|384160|606282|637095|637568|60(?!11))/,
      format: defaultFormat,
      length: [14, 15, 16, 17, 18, 19],
      cvcLength: [3],
      luhn: true
    }, {
      type: 'dinersclub',
      pattern: /^(36|38|30[0-5])/,
      format: /(\d{1,4})(\d{1,6})?(\d{1,4})?/,
      length: [14],
      cvcLength: [3],
      luhn: true
    }, {
      type: 'discover',
      pattern: /^(6011|65|64[4-9]|622)/,
      format: defaultFormat,
      length: [16],
      cvcLength: [3],
      luhn: true
    }, {
      type: 'jcb',
      pattern: /^35/,
      format: defaultFormat,
      length: [16],
      cvcLength: [3],
      luhn: true
    }, {
      type: 'laser',
      pattern: /^(6706|6771|6709)/,
      format: defaultFormat,
      length: [16, 17, 18, 19],
      cvcLength: [3],
      luhn: true
    }, {
      type: 'maestro',
      pattern: /^(5018|5020|5038|6304|6703|6708|6759|676[1-3])/,
      format: defaultFormat,
      length: [12, 13, 14, 15, 16, 17, 18, 19],
      cvcLength: [3],
      luhn: true
    }, {
      type: 'mastercard',
      pattern: /^(5[1-5]|677189)|^(222[1-9]|2[3-6]\d{2}|27[0-1]\d|2720)/,
      format: defaultFormat,
      length: [16],
      cvcLength: [3],
      luhn: true
    }, {
      type: 'unionpay',
      pattern: /^62/,
      format: defaultFormat,
      length: [16, 17, 18, 19],
      cvcLength: [3],
      luhn: false
    }, {
      type: 'visaelectron',
      pattern: /^4(026|17500|405|508|844|91[37])/,
      format: defaultFormat,
      length: [16],
      cvcLength: [3],
      luhn: true
    }, {
      type: 'elo',
      pattern: /^(4011(78|79)|43(1274|8935)|45(1416|7393|763(1|2))|50(4175|6699|67[0-7][0-9]|9000)|627780|63(6297|6368)|650(03([^4])|04([0-9])|05(0|1)|4(0[5-9]|3[0-9]|8[5-9]|9[0-9])|5([0-2][0-9]|3[0-8])|9([2-6][0-9]|7[0-8])|541|700|720|901)|651652|655000|655021)/,
      format: defaultFormat,
      length: [16],
      cvcLength: [3],
      luhn: true
    }, {
      type: 'visa',
      pattern: /^4/,
      format: defaultFormat,
      length: [13, 16, 19],
      cvcLength: [3],
      luhn: true
    }
  ];
```
