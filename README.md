# miniprogram-npm
这是2019年2月13日的记录，简述一下小程序的npm包的安装过程。
解决  工具->构建npm->找不到node_mdules目录的情况。
1、确保本机已安装了node.js，并将node的路径和npm的路径添加到环境变量path中；
2、用powershell输入命令cd 盘符：\小程序的根目录  或者  直接在微信小程序开发者工具中右键打开终端；
3、首先要初始化一下npm， 输入命令： npm init ；
4、这时要设置一下npm的名称等等之类的，随便输入吧。。
5、输入完成后会在终端中出现一个about的小界面；这时微信小程序的根目录下会出现一个package.json的配置文件、package-lock.json的配置文件，一般情况下的找不到node_modules目录就是由于package.json没有出现，因为没有经过初始化这一步；
6、然后安装npm，这里用一个普遍的包举例吧，在终端中输入 npm install miniprogram-datepicker -S --production，等待安装；
7、安装成功，在微信小程序工具中点击 工具->构建npm，等待构建完成，记得还要在详情勾选 使用npm模块 ；
8、在页面的page.json中添加datepicker自定义组件配置
···
{
        "usingComponents": {
        "datepicker": "miniprogram-datepicker"
                           }
}
···
9、在wxml文件中引用datepicker
···
<datepicker value="{{solar}}" bindchange="bindSolarChange">
    <button type="default">公历</button>
</datepicker>
<datepicker value="{{lunar}}" chinese="{{true}}" bindchange="bindLunarChange" picker-class="weui-btn">
    <button type="default">农历</button>
</datepicker>
···
10、完成，在模拟器上预览。
