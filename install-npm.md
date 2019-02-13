# miniprogram-npm
这是2019年2月13日的记录，简述一下小程序的`npm`包的安装过程。<br>
解决  工具->构建`npm-`>找不到`node_mdules`目录的情况。<br>
1、确保本机已安装了`node.js`，并将``node``的路径和`npm`的路径添加到环境变量`path`中；<br>
2、用`powershell`输入命令`cd 盘符：\小程序的根目录`  或者  直接在微信小程序开发者工具中`右键打开终端`；<br>
3、首先要初始化一下`npm`， 输入命令： `npm init` ；<br>
4、这时要设置一下`npm`的名称等等之类的，随便输入吧。。<br>
5、输入完成后会在终端中出现一个`about`的小界面；这时微信小程序的根目录下会出现一个`package.json`的配置文件、`package-lock.json`的配置文件，一般情况下的找不到`node_modules`目录就是由于`package.json`没有出现，因为没有经过初始化这一步；<br>
6、然后安装`npm`，这里用一个普遍的包举例吧，在终端中输入 `npm install miniprogram-datepicker -S --production`，等待安装；<br>
7、安装成功，在微信小程序工具中点击 工具->构建`npm`，等待构建完成，记得还要在详情勾选 `使用npm模块` ；<br>
8、在页面的`page.json`中添加`datepicker`自定义组件配置
```html
{
        "usingComponents": {
        "datepicker": "miniprogram-datepicker"
                           }
}
```
9、在wxml文件中引用datepicker
```html
<datepicker value="{{solar}}" bindchange="bindSolarChange">
    <button type="default">公历</button>
</datepicker>
<datepicker value="{{lunar}}" chinese="{{true}}" bindchange="bindLunarChange" picker-class="weui-btn">
    <button type="default">农历</button>
</datepicker>
```
10、完成，在模拟器上预览。
