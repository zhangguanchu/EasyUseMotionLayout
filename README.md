# EasyUseMotionLayout
快速入门MotionLayout动画



## MotionLayout是什么

简而言之，MotionLayout首先是一个布局（继承自ConstraintLayout），可以定位元素。其次，通过动画的方式来表现View组件之间的动态关系。



## MotionLayout有什么特点

1.MotionLayout的动画是完全声明式的，你完全可以通过xml文件的形式来定义复杂动画。假如你需要在通过Java代码定制动画的话，建议你还是用Property Animation吧。

2.兼容Android SDK最低版本是14（`IceCreateSandwich`）



## MotionLayout怎么导入

当前MotionLayout还是Alpha版本，不太稳定，可能会有命名和API的修改。

```
dependencies {
    implementation 'com.android.support.constraint:constraint-layout:2.0.0-alpha2'
}
```



## MotionLayout你需要知道的概念

![MotionLayout结构](https://github.com/kaershushu/EasyUseMotionLayout/blob/HEAD/art/MotionLayout%E7%BB%93%E6%9E%84.png)

- ConstaintSet:约束，可以简单理解成一个被ConstraintLayout包含的独立的View，实际上Constrait代表的是一个View的约束状态。那么ConstaintSet自然就是一组View的集合了。在MotionLayout的概念里其实就是动画执行起点和终点的一组View的状态。
  
    * CustomAttribute:配合ConstraintSet使用，动画属性，比如颜色，透明度等等。
        
        > attributeName:属性名，一般是`setter`,`getter`方法定义的属性，比如`backgroundColor`。
        > customXXXValue:具体属性值。
  
- MotionScene:产生动画效果的核心，所有的动画效果都是在这个文件里定义。

  - StateSet
  
  - Transition:定义出发动画动作和帧控制，分两种`OnSwipe`和`OnClick`。
  
    * 1.`KeyFrameSet`:帧控制,和ConstraintSet一样，KeyFrameSet可以是一个控制动画集合的参数，配合KeyAttribute或者KeyFramePosition使用。
        
       > KeyAttribute:具体属性,用来控制某一帧的形态变化，比如`旋转`，`缩放`等，并不改变View的大小。
         
       > KeyPosition:某一帧View大小变化。



## 怎样建立一个我们需要的MotionLayout

1.`res`下新建一个`xml`文件夹，用于存放我们需要定义的动画文件。

2.在xml文件夹下新建一个xml文件，`Root Tag`为`MotionScene`。

3.Done！就是这么简单。

## MotionLayout能用来做哪些事情

* ViewPager:当前无法滑动，后边考虑加一下滑动效果

![ViewPager效果](https://github.com/kaershushu/EasyUseMotionLayout/blob/HEAD/art/viewpager.gif)











