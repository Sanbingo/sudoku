使用HTML和CSS实现九宫格列表，设定高度，超过高度的块使用滚动条滚动展示。

**1、html代码**
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <link rel="stylesheet" href="./index.css">
  <title>Sudoku</title>
</head>
<body>
  <div class="square">
    <ul class="square-inner flex">
      <li>1</li>
      <li>2</li>
      <li>3</li>
      <li>4</li>
      <li>5</li>
      <li>6</li>
      <li>7</li>
      <li>8</li>
      <li>9</li>
      <li>10</li>
      <li>11</li>
    </ul>
</div>
</body>
</html>
```
**2、CSS代码**
```
* {
  margin: 0;
  padding: 0;
}
ol, ul {
  list-style: none;
}
.square{
  position: relative;
  width: 300px;
  height: 300px;
}
.square-inner{
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%; /* 铺满父元素容器，这时候宽高就始终相等了 */
}
.square-inner>li{
  width: calc(98% / 3);  /* calc里面的运算符两边要空格 */
  height: calc(98% / 3);
  margin-right: 1%;
  margin-bottom: 1%;
  overflow: hidden;
}

.flex{
  display: flex;
  flex-wrap: wrap;
}
.flex>li{
  flex-grow: 0; 
  background-color: #4d839c;
  text-align: center;
  color: #fff;
  line-height: 2;
}
.flex>li:nth-of-type(3n){ /* 选择个数是3的倍数的元素 */
  margin-right: 0;
}

```
**3、效果**

**4、参考**

https://me.chjiyun.com/2017/12/08/CSS%E5%AE%9E%E7%8E%B0%E8%87%AA%E9%80%82%E5%BA%94%E4%B9%9D%E5%AE%AB%E6%A0%BC%E5%B8%83%E5%B1%80/
