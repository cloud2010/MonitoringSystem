APP开发环境安装
==============

简要概述 Ionic 和 Cordova 开发环境配置

## 1.下载安装[Node.js](https://nodejs.org)

切换NPM安装源为淘宝镜像

```bash
npm config set registry http://registry.cnpmjs.org`
npm info underscore  # 如果上面配置正确这个命令会有字符串response
```

## 2.下载安装 JDK 1.8

配置 `JAVA_HOME` 环境变量，确保 `java javac` 正常访问

## 3.下载安装Android SDK

配置 `ANDROID_HOME`
配置 `%ANDROID_HOME%\platform-tools;%ANDROID_HOME%\tools;`

## 4.下载安装打包工具[Grade](https://gradle.org/)

配置 `GRADE_HOME` 和 `%GRADLE_HOME%\bin`
确保 Cordova 正常编译，请下载 gradle-3.3-all.zip

## 5.NPM安装cordova和ionic

```bash
npm install -g cordova ionic
```

## 6.初始化项目

```bash
ionic start sdscapp --type=ionic1
```

## 7.在对应项目中添加Android平台

可以指定版本

```bash
cordova platform add android@^6.3.0
```

## 8.生成签名文件

参考[链接1](http://www.cnblogs.com/a418120186/p/5475621.html)
参考[链接2](http://www.cnblogs.com/GYZhao/p/6575104.html)

## 9.编译打包

读取编译配置文件来进行编译打包，不带`--release`则为debug版本

```bash
cordova build android --release --buildConfig=..\myBuildConfig.json
```

JSON参考格式
```json
{ 
　　"android": { 
　　　　"release": { 
　　　　　　"keystore": "release-key.keystore", 
　　　　　　"alias": "cordova-demo", 
　　　　　　"storePassword": "testing", 
　　　　　　"password": "testing" 
　　　　}　　 
　　} 
}
```

一般打包方式

```bash
cordova build android --release -- --keystore=smu.keystore --alias=smu-test
```

## Using this project

We recommend using the [Ionic CLI](https://github.com/ionic-team/ionic-cli) to create new Ionic projects that are based on this project but use a ready-made starter template.

For example, to start a new Ionic project with the default tabs interface, make sure the `ionic` utility is installed:

```bash
$ npm install -g ionic cordova
```

Then run:

```bash
$ ionic start myProject tabs --type=ionic1
```

More info on this can be found on the Ionic [Getting Started](https://ionicframework.com/getting-started) page and the [Ionic CLI](https://github.com/ionic-team/ionic-cli) repo.

## Issues

Issues have been disabled on this repo. If you do find an issue or have a question, consider posting it on the [Ionic Forum](https://forum.ionicframework.com/). If there is truly an error, follow our guidelines for [submitting an issue](https://ionicframework.com/submit-issue/) to the main Ionic repository.
