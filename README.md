## 
![](http://ok7n02kz6.bkt.clouddn.com/FqYu_G8VWm6HhR82949Aqi4MVP0L.gif)



## 关键点

- `Element.getBoundingClinentRect()`,通过这个方法我们可以获取到一个元素的大小以及它相对于视口的位置。



### 实现过程

上面我们说到了如何获取一个元素相对于视口的位置，有了这个实现上图中的效果就很容易啦。

- 首先，获取所有的`a`元素

- 其次，创建一个`span`,这样我们的鼠标移动到`a`元素的时候，这个`span`就会移动到相应的`a`元素上。

- 移动的过程(方法)。获取到了`a`元素的位置，也创建好了需要的`span`元素，

  ![](http://ok7n02kz6.bkt.clouddn.com/FtrkIY6MyVM4wPeSPOwcO1I91bDd.png)

  在控制台中我们可以看到`getBoundingClinentRect()`这个方法的返回结果，接下自然就是将`a`元素的位置赋值给`span`元素，这样就可以让`span`元素出现在`a`元素上啦。

  ```javascript
  const coords = {
          width: linkCoords.width,
          height: linkCoords.height,
          top: linkCoords.top + window.scrollY,
          left: linkCoords.left + window.scrollX
  }
  ```

  这里需要注意的一点时，`width`和`height`直接使用了`a`元素的，但是`top`与`left`属性我们却加上了`window.scrollY`以及`window.scrollX`,这是为什么呢，那我们看一下没有加上的话会是什么样的效果吧。

  ![](http://ok7n02kz6.bkt.clouddn.com/FtGECeGMagdoaQxsCZS4Eu1VEUd4.gif)

   当我们滚动页面之后，再将鼠标移动到`a`元素上可以看到会有错误的情况，所以加上滚动的距离也就是`window.scrollY`就可以精确的定位啦。

