![React.js](https://miro.medium.com/max/2456/1*1Z177dpTeAp7uEFc5Zx2xg.png)

动画是 ReactJs 应用程序中一个热门话题，我们有很多方法可以创建不同类型的动画。例如，很多开发人员喜欢使用 css 动画。但如果你想创建更复杂的动画，你可以关注 GreenSock 。GreenSock 是最具影响力的动画平台，同时，它给 React 提供了很多用于创建动画的库或组件。

接下来，进入主题 😎。

1. **CSS 动画**
2. **React-transition-group -**它是一个附加组件，用于实现基本的 CSS 动画和过渡动画。
3. **react-animations -** React-animations 实现 animate.css 的所有动画。简单易用！
4. **React Reveal -**这是 React 的动画框架。
5. **TweenOne -** ant.design 里用于动画的库

> ........................ ...👇 
> 要查看回购，请单击[此处](https://github.com/NozhenkoD/react-animation-2019)。👈 
> ...........................👆

当然，还有很多开源的动画库和组件，但是这篇文章不会涉及这些库。

👨💻让我们开始吧。



### 一、CSS 方法

这种方法是实现动画的最简单、最基础的方式。使用它不需要倒入  JavaScript 库，并且浏览器花费的资源也更少。如果你有一个简单的动画并担心应用程序的大小，可以使用此方法。

那么，如何使用css做动画喃？
我们来看看汉堡菜单示例：👇

![img](https://miro.medium.com/freeze/max/52/1*cosKxTRdOfM3YrNc_2Ah3g.gif?q=20)

此菜单易于使用，具有 css 属性和 `className="is-nav-open"` html 标记的触发器。有很多方法可以实现这个例子。其中之一是在导航上方创建一个包装器并触发保证金的更改。导航具有恒定的宽度相等 `250px` 。包装带有 `margin-left` 或 `translateX` 具有相同宽度的属性。当我们需要显示导航时，我们必须 `className="is-nav-open"` 为包装器添加导航并移动包装器 `margin-left/translateX: 0;` 

![img](https://miro.medium.com/max/60/1*cfVr3j7sa2sgpaM9R60Fqg.png?q=20)

和 CSS 风格：

![img](https://miro.medium.com/max/32/1*nZ6Mq1wmqu8JSF-DfebeVw.png?q=20)

相信我，在大多数情况下都需要使用这种方法。我们生活得更好写作几个 css 行并触发 className ，而不是导入大型库并在项目中实现它。用户将非常感谢您的浏览器快速复制应用程序。

但有时候，你必须使用其他方法。还有其他什么方法？让我们来看看下一个方法。



### 二、 ReactTransitionGroup

这个附加组件是由ReactJs社区的人员开发的。[ReactTransitionGroup](https://github.com/reactjs/react-transition-group)很容易实现基本的CSS动画和过渡。

开发人员将此库描述为：

> “用于管理组件状态（包括安装和卸载）的一组组件，特别是考虑到动画而设计的。”

无论如何，关于它的附加组件需要了解三件事：

- 当组件生命周期发生更改时，React Transition Group会更改类。反过来，应该在CSS类中描述动画样式。
- ReactTransitionGroup的大小很小。它应该安装在React应用程序的包中，不会显着增加您的捆绑包。但你可以使用CDN。
- ReactTransitionGroup有3个组件（Transition，CSSTransition和TransitionGroup）。为了获得动画，您需要将组件包装在其中。

让我们来看看如何制作类似的动画*👀👇*

![img](https://miro.medium.com/freeze/max/60/1*AwFrD7KVn0gibJX5iVT5BA.gif?q=20)

首先，你需要导入`CSSTransitionGroup`的`react-transition-group`。之后你必须将列表包装在其中并设置`transitionName`道具。每当`CSSTransitionGroup`添加或删除子项时，它将获得动画样式。

![img](https://miro.medium.com/max/60/1*ltbYH9Yv8WPH5Jzs3koYKQ.png?q=20)

如果设置了`transitionName="example"`props，则样式表中的类应以示例名称开头。

![img](https://miro.medium.com/max/56/1*qM3rFr4M1awe5m4G92CPbg.png?q=20)

您可以看到基本用法`ReactTransitionGroup`版本。👀

这就是你需要的一切。当然，您需要添加一些逻辑。我们应该描述两种方法来实现我们的示例联系人列表：

`handleAdd` - 添加新的联系人，它获得一个随机名称并将其推送到数组state.items。（它使用随机名称包随机名称）

`handleRemove`- 通过`state.items`数组中的索引删除联系人。

![img](https://miro.medium.com/max/36/1*q9k9_wlw109fXtC3458mbQ.png?q=20)



### 三、 反应过来的动画

[React-animations](https://github.com/FormidableLabs/react-animations) - 该库是使用[animate.css](https://daneden.github.io/animate.css/)构建的所有动画。它易于使用，并有很多动画集合。React-animation适用于任何支持使用对象定义关键帧动画的内联样式库，例如Radium，Aphrodite或样式组件。我更喜欢使用样式组件。

*你可以在gif上看到一些动画：👀👇*

![img](https://miro.medium.com/freeze/max/54/1*2SJH2tItiljweyRgivf9JQ.gif?q=20)

我知道你的想法😄

![img](https://miro.medium.com/freeze/max/60/1*1VZUa3mn3569l3ePzq3piA.gif?q=20)

一旦你看到这些动画，你就会意识到你可以在哪里使用它们。
我们来看看它是如何工作的。例如 - **Bounce动画**。

![img](https://miro.medium.com/freeze/max/60/1*bkPR-nhoZ5aTw_et9Mt7Ow.gif?q=20)

从中导入所选动画所需的第一件事`react-animations`。

正如我之前提到的，在使用动画样式和基本关键帧创建包装组件之后，我使用了样式组件。

![img](https://miro.medium.com/max/60/1*SHl61xR75pQ5V5nVohu7Tg.png?q=20)

创建组件时，您需要包装任何**HTML**或动画组件。

![img](https://miro.medium.com/max/60/1*K79gjVVrNwV-XS23dZYywA.png?q=20)

例：

![img](https://miro.medium.com/max/60/1*WHA_BeFNgOK2FfzV2SGo_A.png?q=20)

动画有效。这个动画是基本的，很容易。

滚动时使用此动画有一些很好的解决方案 - [react-animate-on-scroll](https://dbramwell.github.io/react-animate-on-scroll/#home)。



### 四、 反应，揭示

[React Reveal](https://www.react-reveal.com/)是[React](https://www.react-reveal.com/)的动画框架。它具有基本动画，如淡入淡出，翻转，缩放，旋转和许多更高级的动画。它允许您使用道具控制所有动画，例如：位置，延迟，距离，级联等等。你可以[在这里](https://www.react-reveal.com/docs/props/)看到它们。您还可以使用自定义CSS效果。它还具有服务器端渲染和高阶组件。如果您喜欢使用动画滚动此框架。看看它是如何工作的。

![img](https://miro.medium.com/max/60/1*zlan6j1-GWgv4RMSgQP92w.png?q=20)

让我们看看这个动画的滚动效果。*👀👇*

![img](https://miro.medium.com/freeze/max/60/1*Xk4c0gzjEu8RCsCyVRPlYg.gif?q=20)

我们有5个街区，每个街区都有一个全屏页面和一个标题。

![img](https://miro.medium.com/max/44/1*GzSUQvXa8nJrlgGnqT6eRQ.png?q=20)

我们创造`animateList`恒定。该数组包含5个元素。使用数组方法后，`map`您可以渲染`Fade`组件中的每个元素并将项目插入标题。Const样式具有我们的块和标题的短css样式。我们`Fade`从顶部有5个动画块。



### 五、TweenOne 和 Ant 设计中的**一个** animation **。**

[Ant Design](http://ant.design/)是一个React UI库，它是一个易于使用的组件。它是构建优雅用户界面的有用组件。Ant Design由中国企业集团阿里巴巴创建，它使用了很多知名品牌：阿里巴巴（当然），腾讯，百度等等。

您可能已经听说过Ant设计，所以让我们在其着陆页上考虑它的动画

![img](https://miro.medium.com/freeze/max/60/1*_6S4VTzzGwRtebx-ys4htA.gif?q=20)

如你所见，有很多动画元素。我想给你看一个简短版本，因为所有元素都有类似的动画。我选择了地球上的绿球和背景上的一个元素，例如红色方块。我们的动画看起来像这样。

![img](https://miro.medium.com/freeze/max/60/1*awI1UedVjvAwINK3lwCsyA.gif?q=20)

我`TweenOne`在这个动画中使用了组件，但它需要`PathPlugin`在动画中使用路径。当你按下它会工作`PathPlugin`到`TweenOne.plugins`。

![img](https://miro.medium.com/max/60/1*Tf876Sktjm4nCtGIpHOWwQ.png?q=20)

下一步让我们描述一下Basic动画参数：

- **持续时间 -**以毫秒为单位的动画
- **轻松** - 动画轻松，
- **yoyo -**每次重复都向前和向后交替。
- **重复** - 重复动画。您必须使用-1进行无限期处理。
- **p** - 动画的路径坐标
- **easePath** - 动画的缓动路径坐标

你不必担心最后两个参数对于这个svg更具体。

![img](https://miro.medium.com/max/60/1*4saA8U2k7uFNtiH4gX5qUg.png?q=20)

接下来我们将创建一个动画对象。该对象有3种类型的动画：

- **redSquare** - 它有循环参数，我们在下面描述，以及Y坐标，持续时间和延迟。
- **greenBall** - 它有对象参数的路径`x`，`y`是值`p`。持续时间，重复和轻松 - `TweenOne.easing.path`- 两个参数的功能：
- **path -** easePath坐标。
- **lengthPixel -**将分割曲线分为400个部分。
- **track** - 一个带有轴的椭圆形，具有循环样式和旋转参数。

![img](https://miro.medium.com/max/60/1*F5wl-UcUTTgezbJZEZCbVA.png?q=20)

您无需担心此代码。你必须注意`TweenOne`组件。让我们简单地提醒一下，这些组件将从中导入`rc-tween-one`。它被用作基础道具和动画道具的基本组件。这是我们的动画！每一个`TweenOne`都有它自己的动画规则`redSquare`，`track`，`greenBall`。

![img](https://miro.medium.com/max/36/1*ZcVb5saeoTkdTWJRrQ2cAQ.png?q=20)

![img](https://miro.medium.com/freeze/max/60/1*lIUAJ_Cu6PgTrL6MLj1uvA.gif?q=20)

😄看起来吓人。但事实上，你需要注意这些线条。

![img](https://miro.medium.com/max/60/1*3dRieGpfKGgRPQfPeu9L5Q.png?q=20)

正如您所注意到的，使用此方法创建动画是一种简单的方法。您所需要的只是描述动画规则并将它们传输到`TweenOne`组件。



###  🏁结论

使用动画有很多方法。所有这些都需要不同的方法。今天我们已经回顾了您可以在项目中使用的一些决策。选择适合你的方法👨💻

before您的网站在阅读本文之前：

![img](https://miro.medium.com/max/60/1*mOtJ8bBGfStPvdrEClqYhQ.png?q=20)

after阅读本文后您的网站：

![img](https://miro.medium.com/freeze/max/60/1*emR9fk9Kt80Dugw5VSNkQA.gif?q=20)

😄明智地使用动画！

------

> 👇你还应该阅读下一篇文章：👇

1. [**使用Sentry跟踪React App中的错误**](https://medium.com/hackernoon/tracking-errors-in-react-app-with-sentry-d6091a84b64e)
2. [**在React JS中实现CSS的9种方法**](https://medium.com/@dmitrynozhenko/9-ways-to-implement-css-in-react-js-ccea4d543aa3?source=friends_link&sk=0497aa32141ac0a444bc088efadc4cad)



### ❤️感谢阅读

玩得开心，不断学习，并始终保持编码。
关注[**Medium**](https://medium.com/@dmitrynozhenko)＆[**Linkedin**](https://www.linkedin.com/in/dmitry-nozhenko-772a2195/)。



### 👏喜欢，分享，发表评论

如果您有任何问题或反馈，请在下面的评论中告诉我们👇

![img](https://miro.medium.com/freeze/max/60/1*itETjI1PFdtVKZvp5Qusxw.gif?q=20)

> 下面你可以看到一个流行的动画库列表的奖金。

> ReactJs库：

1. [**react-motion**](https://github.com/chenglou/react-motion) - 解决动画问题的弹簧。
2. [**react-spring**](https://github.com/react-spring/react-spring) - 基于Spring物理的 *React* *动画*库。
3. [**ant-motion**](https://github.com/ant-design/ant-motion) - Ant设计的Animate规范和组件。
4. [**反应-移动**](https://github.com/react-tools/react-move) -美丽的，数据驱动*的动画*用于*反应。*
5. [**react-flight**](https://github.com/jondot/react-flight) -为 *React*构建*动画*作品的最佳方法。
6. [**react-flip-move**](https://github.com/joshwcomeau/react-flip-move) -使用FLIP技术在DOM更改（例如列表重新排序）之间轻松进行*动画*。
7. [**react-burger-menu**](https://github.com/negomi/react-burger-menu) - 使用CSS过渡和SVG路径*动画的*一个带有一系列效果和样式的画布边栏组件*。*
8. [**动画**](https://github.com/animatedjs/animated) -用于 *React*和 *React* Native的声明性*动画*库
9. [**react-tween-state**](https://github.com/chenglou/react-tween-state) -*反应* *动画*。
10. [**react-animations**](https://github.com/FormidableLabs/react-animations) - 内联样式库的动画集合

> Javascript库：

1. [**GSAP**](https://greensock.com/) - 适用于现代网络的超高性能专业级动画
2. [**Anime.js**](https://github.com/juliangarnier/anime/) - Anime.js（`/ˈæn.ə.meɪ/`）是一个轻量级JavaScript动画库，具有简单但功能强大的API。
   它适用于CSS属性，SVG，DOM属性和JavaScript对象。
3. [**Popmotion**](https://github.com/Popmotion/popmotion) - 用于令人愉悦的用户界面的简单动画库。
4. [**vivus**](https://github.com/maxwellito/vivus) - 在SVG上制作绘图动画的JavaScript库。
5. [**svg.js**](https://github.com/svgdotjs/svg.js) - 用于操作和动画SVG的轻量级库。
6. [**velocity**](https://github.com/julianshapiro/velocity) - Velocity是一个动画引擎，与jQuery的 *$ .animate（）*具有相同的API。
7. [**哇**](https://github.com/matthieua/WOW) - 滚动时显示动画。非常Animate.css朋友。
8. [**dynamic.js**](https://github.com/michaelvillar/dynamics.js/) - 用于创建基于物理的动画的Javascript库。
9. [**granim.js**](https://github.com/sarcadass/granim.js) - 使用这个小的JavaScript库创建流畅的和交互式的渐变动画。
10. [**kute.js**](https://github.com/thednp/kute.js/) - KUTE.js是一个原生的JavaScript动画引擎，具有出色的代码质量和badass性能
11. [**TweenJs**](https://github.com/CreateJS/TweenJS) - 一个简单但功能强大的Javascript补间/动画库。CreateJS库的一部分。
12. [**moveTo**](https://github.com/hsnaydd/moveTo) - 一个没有任何依赖关系的轻量级滚动动画javascript库
