# 项目说明

此项目为[运维咖啡吧](https://ops-coffee.cn)网站里的猫实现代码

欢迎关注作者微信公众号，里边有更多干货内容

![欢迎关注微信公众号【运维咖啡吧】](/images/qrcode.jpg)

配合对应文章看源码更有效：







# 几行代码养只猫，心情瞬间好多了

> 或枯燥或有趣的技术学习，都不妨碍一只憨态可掬的萌猫卧在你的网页上

浏览博客的时候经常会看到一个二次元的小姐姐或轻轻摇头或眨巴眼睛似在与你互动甚是可爱，就像下边这样

![img](https://blz.nosdn.127.net/sre/images/20190619.live2d.1.gif)

曾想了解是如何实现的，奈何本身不懂前端，且对二次元并不感冒，就放下了，直到遇到了这只猫，再也无法抵挡诱惑，决心将她抱进自己的博客，每天能看到她，就会有个好心情，我想也许会有读者跟我一样吧，能有这么一只萌宠呆在这里足以平添很多的乐趣了

![img](https://blz.nosdn.127.net/sre/images/20190619.live2d.2.gif)

以上这种效果都是使用Live2D技术实现的，Live2D是一种应用于电子游戏的绘图渲染技术，由日本Cybernoids公司开发，通过一系列的连续图像和人物建模来生成一种类似二维图像的三维模型，换句话说就是2D的素材实现一定程度的3D效果

Live2D可以展示在很多平台上，例如浏览器，Android，IOS，Unity等，GitHub上有很多已经实现的Live2D项目，我所养的这只猫也来自于[`live2DModel`](https://github.com/QiShaoXuan/live2DModel)这个仓库，这个仓库下还收集了其他一些Live2D模型

在自己的网站上养猫非常的简单，只需要以下两步即可，其实[`live2DModel`](https://github.com/QiShaoXuan/live2DModel)仓库里边有demo的，但是对于完全不懂前端的人来说看起来还是有点费劲，我这里仅仅是给整理成更容易理解和使用的版本，向原作者致敬：

1. 下载代码仓库到自己的项目下，仓库地址如下：

```
https://github.com/ops-coffee/demo/tree/master/live2d
```

其中index.hmtl为示例代码，将整个项目放在nginx下可以直接查看效果

live2d文件夹存放了猫的模型以及需要用到的两个js文件

你只需要把index.html同层的live2d文件夹拷贝到你的项目下，然后按照下边步骤添加js就可以将猫养在你的站点了

1. 添加如下JS代码到需要显示猫的页面上

```
<script src="/live2d/L2Dwidget.min.js"></script>
<script type="text/javascript">
  L2Dwidget.init({
    model: {
      jsonPath: '/live2d/tororo/assets/tororo.model.json',
    },
    display: {
      superSample: 2,
      width: 150,
      height: 150,
      position: 'right',
      hOffset: 0,
      vOffset: 0,
    },
    mobile: {
      show: true,
      scale: 1,
      motion: true,
    },
    react: {
      opacityDefault: 0.8,
      opacityOnHover: 0.2,
    }
  })
</script>
```

**model：** 指定`model.json`位置，如果你不喜欢猫也可以在[`live2DModel`](https://github.com/QiShaoXuan/live2DModel)这个仓库下查找自己喜欢的模型，然后将模型目录拷贝到live2d文件夹下，然后修改model路径参数以及display显示参数即可

**display：** 控制live2d模型在页面上显示的位置

**mobile：** 控制手机上是否显示

**react：** 控制显示的透明度

至此完成，再访问网页就会发现一只猫静静的卧在那里，看风云变幻，自云淡风轻~