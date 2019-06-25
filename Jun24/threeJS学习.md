https://www.cnblogs.com/yeyunfei/p/7899613.html(用webgl[three.js]搭建一个3D库房)

基础教程(http://www.hewebgl.com/article/articledir/1)

## 基础教程 第一张 学习笔记

[TOC]

### 验证Threejs确实启动

我们用Chrome浏览器打开上面的那个网页，打开调试窗口，并在Console下输入  THREE.REVISION  命令    可以查看three.js文件的版本号

### 三大组建 	

 		在Three.js中，要渲染物体到网页中，我们需要3个组建：场景（scene）、相机（camera）和渲染器（renderer）。有了这三样东西，才能将物体渲染到网页中去。 	

 		记住关建语句：有了这三样东西，我们才能够使用相机将场景渲染到网页上去。 	

 		创建这三要素的代码如下： 	

```javascript
var scene = new THREE.Scene();  // 场景
var camera = new THREE.PerspectiveCamera(75, window.innerWidth/window.innerHeight, 0.1, 1000);// 透视相机
var renderer = new THREE.WebGLRenderer();   // 渲染器
renderer.setSize(window.innerWidth, window.innerHeight);    // 设置渲染器的大小为窗口的内宽度，也就是内容区的宽度
document.body.appendChild(renderer.domElement);
```

- #### 场景

  在Threejs中场景就只有一种，用THREE.Scene来表示，要构件一个场景也很简单，只要new一个对象就可以了，代码如下：

   		var scene = new THREE.Scene(); 	

   		场景是所有物体的容器，如果要显示一个苹果，就需要将苹果对象加入场景中。 

- ####  相机

  ​        相机决定了场景中那个角度的景色会显示出来。相机就像人的眼睛一样，人站在不同位置，抬头或者低头都能够看到不同的景色。 	

   		场景只有一种，但是相机却又很多种。和现实中一样，不同的相机确定了呈相的各个方面。比如有的相机适合人像，有的相机适合风景，专业的摄影师根据实际用途不一样，选择不同的相机。对程序员来说，只要设置不同的相机参数，就能够让相机产生不一样的效果。 	

   		在Threejs中有多种相机，这里介绍两种，它们是： 	

   		透视相机（THREE.PerspectiveCamera）、这里我们使用一个透视相机，透视相机的参数很多，（http://www.hewebgl.com/article/getarticle/59）

```javascript
var camera = new THREE.PerspectiveCamera(75, window.innerWidth/window.innerHeight, 0.1, 1000);
```

- #### 渲染器 	

   		最后一步就是设置渲染器，渲染器决定了渲染的结果应该画在页面的什么元素上面，并且以怎样的方式来绘制。这里我们定义了一个WebRenderer渲染器，代码如下所示： 	

```javascript
var renderer = new THREE.WebGLRenderer();
renderer.setSize(window.innerWidth, window.innerHeight);
document.body.appendChild(renderer.domElement);
```

- #### 添加物体到场景中

```
//添加物体到场景中
//THREE.CubeGeometry是一个几何体,其中三个参数 分别是
//width：立方体x轴的长度
//height：立方体y轴的长度
//depth：立方体z轴的深度，也就是长度 
var geometry = new THREE.CubeGeometry(1,1,1); 
var material = new THREE.MeshBasicMaterial({color: 0x00ff00});
var cube = new THREE.Mesh(geometry, material); 
scene.add(cube);
```

- 渲染

 		渲染应该使用渲染器，结合相机和场景来得到结果画面。实现这个功能的函数是 	

 		renderer.render(scene, camera); 	

 		渲染函数的原型如下： 	

 		render( scene, camera, renderTarget, forceClear ) 	

 		各个参数的意义是： 	

 		scene：前面定义的场景 	

 		camera：前面定义的相机 	

 		renderTarget：渲染的目标，默认是渲染到前面定义的render变量中 	

 		forceClear：每次绘制之前都将画布的内容给清除，即使自动清除标志autoClear为false，也会清除。 	

- #### 渲染循环 	

   		渲染有两种方式：实时渲染和离线渲染 。 	

      		 先看看离线渲染，想想《西游降魔篇》中最后的佛主，他肯定不是真的，是电脑渲染出来的，其画面质量是很高的，它是事先渲染好一帧一帧的图片，然后再把图片拼接成电影的。这就是离线渲染。如果不事先处理好一帧一帧的图片，那么电影播放得会很卡。CPU和GPU根本没有能力在播放的时候渲染出这种高质量的图片。 	

      		实时渲染：就是需要不停的对画面进行渲染，即使画面中什么也没有改变，也需要重新渲染。下面就是一个渲染循环： 	

  ```
  function render() {
      cube.rotation.x += 0.1;
      cube.rotation.y += 0.1;
      renderer.render(scene, camera);
      requestAnimationFrame(render);
  }
  ```

  其中一个重要的函数是requestAnimationFrame，这个函数就是让浏览器去执行一次参数中的函数，这样通过上面render中调用requestAnimationFrame()函数，requestAnimationFrame()函数又让rander()再执行一次，就形成了我们通常所说的游戏循环了。