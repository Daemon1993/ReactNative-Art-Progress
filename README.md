# ReactNative-Art-Progress
CircleProgress  base  on ReactNative ART 

重点实现进度的核心就两个

- 一个是根据角度计算终点坐标 sin cos
- 一个是push方法 用圆弧 将两个点连起来

> 效果图
>>![效果图](http://upload-images.jianshu.io/upload_images/831873-35605fb34b5078d3.gif?imageMogr2/auto-orient/strip)

![内容说明](http://upload-images.jianshu.io/upload_images/831873-d7f29f111bc27fc3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


>使用方法很简单

````
               <CircleProgressView progress={this.state.progress}>
                    <View style={{backgroundColor: '#987123', flex: 1,  alignItems: 'center'}}>
                        <Text>外部放入进度条中间的内容</Text>
                    </View>
                </CircleProgressView>

                <AnimatedCircleProgress progress={this.state.progress}>
                    <View style={{backgroundColor: '#987123', flex: 1,  alignItems: 'center',justifyContent:'center'}}>

                        <AMAText value={this.state.progress}/>

                    </View>
                </AnimatedCircleProgress>

````

![一个无动画 一个有动画](http://upload-images.jianshu.io/upload_images/831873-863e08fd81b5e4ec.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 复杂配置
![很多的配置](http://upload-images.jianshu.io/upload_images/831873-db6733ad4bd156ac.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

---

>因为进度条是一个单独的组件 所以中间部分 我没有写死
中间区域留了一个位置
可以插入你想插入的View

效果图中间的数字动画使用Animated.createAnimatedComponent实现
- 中间留空的区域 是根据传入的半径 获取到了圆的区域 在计算中间内切正方形的区域 在通过绝对布局left top实现 具体可以看代码

---
>代码就不贴了  github有
如果对RN的ART arcTo 圆弧 不太熟悉的 可以看看Demo 希望有帮助

[详细解说介绍地址--->(learn more)](http://www.jianshu.com/p/c11c2d2beca6)