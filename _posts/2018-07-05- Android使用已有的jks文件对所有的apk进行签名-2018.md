
先找将已有的jsk文件和apk放到JavaJdk的bin目录下 如果不这样的话可能再运行命令的时候报“ 不是内部或外部命令，也不是可运行的程序 或批处理文件。”的错误

  然后通过cmd命令进入bin目录下

使用命令行进行签名。 
android有自带签名的DOS命令 : jarsigner -verbose -keystore [您的私钥存放路径] -signedjar [签名后文件存放路径] [未签名的文件路径] [您的证书名称] 
此命令各参数含义如下： 
jarsigner -verbose -keystore zdd.keystore -signedjar 123x.apk 
456.apk asia

jarsigner -verbose:签名命令标识符。 
-keystore:后面跟着的是你签名使用的密钥文件(keystore)的绝对路径。 
-signedjar:此后有三个参数： 
参数一:签名后生成的apk文件所要存放的路径。 
参数二:未签名的apk文件的存放路径。 

参数三:你的证书名称，通俗点说就是你keystore文件的别名，那这个别名怎么查看？其实就是在你eclipse或studio进行签名打包时的Alias的值。





如果这个值填写不正确就会出现： 

jarsigner: 找不到zdd.keystore的证书链。zdd.keystore必须引用包含私有密钥和相应的公共密钥证书链的有效密钥库密钥条目

签名按照以上命令格式，按回车键输入密钥库的密码短语（如果密码是数字是不会显示的）再按回车键就会在你所给的路径生成一个签名apk。 




注意签名后生成的apk文件所要存放的路径最好不要用当前bin目录的路径 否则会生成失败 最好用D盘或者E盘 
