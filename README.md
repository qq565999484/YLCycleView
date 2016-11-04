# YLCycleView
Swift无限轮播
##如何使用？
####Demo运行会报错。请你务必对demo进行 pod install
###把<font color=#0099ff size=14 face="黑体">YLCycleView</font>文件夹拖入你的项目
  ```Swift
        let images = ["http://c.hiphotos.baidu.com/image/pic/item/b58f8c5494eef01f50d40bbee5fe9925bd317d8c.jpg", "1", "2", "3", "4"]
        let titles = ["Raindew","无限轮播", "QQ群：511860085", "欢迎加入", "帅的人已经Star"]
        let cycleView = YLCycleView(frame: CGRect(x: 0, y: 100, width: self.view.bounds.width, height: 150), images: images, titles: titles)
        view.addSubview(cycleView)
  ```
  你可以在把本地图片名称直接放进数组里，也可以放一个URL
  为了方便网络图片，我做了这样一个处理，但是同时我需要麻烦你在项目中引入[Kingfisher](https://github.com/onevcat/Kingfisher) 这个三方
###如果你想获取点击事件请设置代理并且遵守它！最后实现代理方法。如果你不需要，忽略它。
  ```Swift
     cycleView.delegate = self;
     func  clickedCycleView(_ cycleView : YLCycleView, selectedIndex index: Int) {
        print("点击了第\(index)页")
    }
  ```
###大多数而言，这个滚动视图都是有一个<font color=#0099ff size=14 face="黑体">title</font>的。当然如果你不需要直接这样创建视图:
  ```Swift
        let cycleView = YLCycleView(frame: CGRect(x: 0, y: 100, width: self.view.bounds.width, height: 150), images: images)
  ```
##重要提醒：如果你使用了导航，那么你必须在使用控制器中设置滚动偏移，复制下面一行代码到你的控制器中
```Swift
 self.automaticallyAdjustsScrollViewInsets = false
```
##效果图
![image](https://github.com/Rain-dew/YLCycleView/blob/master/YLCycleViewDemo/YLCycleViewDemo/%E6%95%88%E6%9E%9C.gif)

#YLSinglerowView
##如何使用？
  ```Swift
  
        let singlerView = YLSinglerowView(frame: CGRect(x: 50, y: 350, width: 200, height: 30), scrollStyle: .up, roundTime: 5, contentSource: ["这是一条重大新闻","吃货节到了钱包准备好了吗","独家福利来就送!"], tagSource: ["新闻", "吃货节", "福利"])
        singlerView.delegate = self
        //更多公开属性自行查找
        //        singlerView.backColor = .darkGray
        //        singlerView.contentTextColor = .purple
        //        singlerView.tagBackgroundColors = [.white,.yellow,.cyan]
        //        singlerView.tagTextColors = [.red,.blue,.black]

        view.addSubview(singlerView)
  ```
###重要提醒：如果你使用了导航，那么你必须在使用控制器中设置滚动偏移，复制下面一行代码到你的控制器中
```Swift
 self.automaticallyAdjustsScrollViewInsets = false
```
##点击跳转代理
```Swift
    //MARK: -- YLSinglerViewDelegate
    func singlerView(_ singlerowView: YLSinglerowView, selectedIndex index: Int) {
        print("点击了第\(index)个数据")
    }
```
##效果scrollStyle: .up（上下左右皆可滚动）
![image](https://github.com/Rain-dew/YLCycleView/blob/master/YLCycleViewDemo/YLCycleViewDemo/up.gif)
###如果scrollStyle: .left
![image](https://github.com/Rain-dew/YLCycleView/blob/master/YLCycleViewDemo/YLCycleViewDemo/singer1.gif)
###如果你希望设置更多属性，例如字体背景颜色等。打开上面代码注释
![image](https://github.com/Rain-dew/YLCycleView/blob/master/YLCycleViewDemo/YLCycleViewDemo/singer2.gif)


