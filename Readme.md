## 图片转字符工具
- 目标: 图片转换为字符串
- 需求:
    * 常用图片格式均能解析: jpg/jpeg/png/bmp/gif
    * 图片转换为合适大小的字符串(以列宽度为标准,行根据图片比例自动缩放)
        - 大: 正常编码列宽度(100)
        - 中: 50
        - 小: 25
        - 指定
    * 深浅字符串设定 
- 思路与设计:
    * 基本原理: 像素 --> 数字                            --> 填充字符
    * 简单模式: 像素 --> RGB数字,取平均值 --> 填充单个字符
    * 复杂模式: 
        - 按照像素的深浅填充不同字符填充多个字符
        - 按照指定矩形大小(比如四方格,九宫格或更大格子数)的多个像素去填充多个字符中最相似的(每个对应的格子差的绝对值的和最小的)
- 深浅字符的分析
    * 人眼识别: "@#&$%*o!;. "或"M8V|:. "
    * 程序判断: 利用单个字符生成一张小图片,计算这个图片所有像素点的RGB总值,然后进行排序
- 参考:
    * [Swift 实现图片转字符画的功能](http://blog.csdn.net/baisnsf/article/details/46670715)
    * [java图像转码为字符画](http://blog.csdn.net/Al_assad/article/details/53209349)

## 九宫格分析
![九宫格分析](https://github.com/hepengju/img2txt/blob/master/doc/%E4%B9%9D%E5%AE%AB%E6%A0%BC%E5%88%86%E6%9E%90.png)
## 效果示例
![ASCII](https://github.com/hepengju/img2txt/blob/master/example/ASCII%E5%A4%8D%E6%9D%82%E7%89%88.png)
![Unicode](https://github.com/hepengju/img2txt/blob/master/example/Unicode%E5%A4%8D%E6%9D%82%E7%89%88.png)
