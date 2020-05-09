```php
    //定义字符串变量
    $name='黑羊';
    //定义数字变量
    $date=2020;
    //定义数组
    $studying=array("php","html","css","javastript");
    //变量字符串混合输出
    echo ">> 现在是".$date."年，".$name."正在学习".$studying[0]."。";
    //将数组转为json输出
    echo json_encode($studying);

    >>
```
