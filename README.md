### mapping文件
/Users/surao/Desktop/golaxyDev/golaxy/app/build/outputs/mapping.txt

### 配置和切换多java环境
1. open ~/.bash_profile
2. export JAVA_8_HOME=$(/usr/libexec/java_home -v1.8)
   export JAVA_11_HOME=$(/usr/libexec/java_home -v11)

   alias java8='export JAVA_HOME=$JAVA_8_HOME'
   alias java11='export JAVA_HOME=$JAVA_11_HOME'

   # default to Java 11
   java11
3. source ~/.bash_profile
4. 切换时用 java8 或者 java11 切换

### 上传命令：
sudo java -jar buglyqq-upload-symbol.jar
-appid 21ba13754b
-appkey 82f8ace3-516f-4e30-8c1c-fff892d9ccc0
-bundleid com.golaxy.mobile
-version 3.7.0
-platform Android
-inputSymbol /Users/surao/Desktop/golaxyDev/golaxy/app/build
-inputMapping /Users/surao/Desktop/golaxyDev/golaxy/app/build/outputs/mapping/golaxyRelease/mapping.txt


java -jar buglyqq-upload-symbol.jar -appid 21ba13754b -appkey 82f8ace3-516f-4e30-8c1c-fff892d9ccc0 -bundleid com.golaxy.mobile -version 3.7.2 -platform Android -inputSymbol /Users/surao/Desktop/golaxyDev/golaxy/app/build -inputMapping /Users/surao/Desktop/golaxyDev/golaxy/app/build/outputs/mapping/golaxyRelease/mapping.txt
### 代码编写规范
1.数据类型转换（如 praseInt ）一定要加try catch
2.数组，列表使用时一定要判空
3.字符串使用时一定判空

### 编译命令 

./gradlew album:assemble

### 发版修改点：
1. app下gradle中         versionCode 3401 ；versionName "3.4.1"
2. Api中 注意baseurl
## 查看依赖树的方法：
- ./gradlew 模块名：dependencIEs  //查看单独模块的依赖
- ./gradlew -q :app:dependencies //查看项目依赖树
- ./gradlew :app:dependencIEs --configuration compile //查看项目的编译依赖
- ./gradlew :app:dependencyInsight --configuration baiduDebugRuntimeClasspath --dependency com.squareup.okio:okio

## 查看栈中activity
- adb shell
- dumpsys activity activities | grep "Hist"  | grep "com.golaxy"

## 查看当前activity
- adb shell "dumpsys window | grep mCurrentFocus"

## 全局弹窗用透明的activity实现，参考：https://www.jianshu.com/p/26b54897d260
