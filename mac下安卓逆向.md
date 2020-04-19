## mac下安卓逆向

工具：
- brew install apktool
- brew install dex2jar
- JD-GUI：http://jd.benow.ca/

```bush
apktool d xxx.apk    //apk
apktool b xxx        //文件夹
cd 到 文件夹内 build/apk 找到classes.dex
d2j-dex2jar classes.dex -o test.jar
```
