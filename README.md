# liyan_shuzhixinxi

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).




#  遇到的问题



笔试链接及要求：
一、笔试题
https://docs.qq.com/doc/DZHNKY2lqenlCa2lS
二、笔试要求
1、请独立完成笔试题目，可以上机操作，不得百度查找答案；
2、答案需提供实现效果和代码截图；
3、填写完毕后，发送邮箱至2213496732@qq.com（附自己姓名）
4、限12小时内完成
5、把源码放到gitee或者 github上，邮箱就填名字还有仓库地址即可
6、重要提示，答题独立完成
7、尽量今天或明天完成，完成后截图





# 第一题

​            1.     在Vue.js项目中，你正在开发一个组件，该组件包含两个子元素（.container和.content），要求如下：

​            1.     .container元素是一个具有固定宽度且自适应高度的居中容器，其背景颜色为浅灰色。当浏览器窗口尺寸改变时，容器的高度需要保持与内容区域（.content）相同，但不超过屏幕高度的80%。

               2.     .content元素应当在其父元素.container内部水平垂直居中，并且内容自适应高度。同时，.content区域的高度需要根据内部动态内容实时更新，并且在高度变化时有一个平滑过渡效果。

问题: 

vue.js 是什么 怎么设置vue.js项目

vue.js 依赖于nodejs 是基于nodejs的一个框架,

nodejs下载地址:https://nodejs.org/en/download/

但是因为node的版本很多,所以使用nvm  (node version manager)管理node

https://github.com/coreybutler/nvm-windows

 使用18版本

`nvm install 18`

`nvm use 18`

`node --version`



vue 目前有vue2 和vue3  



Vue 实例有一个完整的生命周期，这是由于它的创建、更新、销毁等过程中的一系列钩子函数。以下是 Vue 2 和 Vue 3 中生命周期钩子函数的列表和解释：

### Vue 2 生命周期钩子：

- **beforeCreate**: 在实例初始化之后，数据观测 (data observer) 和事件/watcher 设置之前被调用。

- **created**: 在实例创建完成后被立即调用，此时已完成数据观测、属性和方法的运算，`$el` 属性还未存在。

- **beforeMount**: 在挂载开始之前被调用，相关的 `render` 函数首次被调用。此时 `$el` 属性仍然不可见。

- **mounted**: `el` 被新创建的 `vm.$el` 替换，并挂载到实例上去之后调用该钩子。如果 `root` 实例挂载了一个文档内元素，当 `mounted` 被调用时 `vm.$el` 也在文档内。

- **beforeUpdate**: 数据更新时调用，发生在虚拟 DOM 打补丁之前。这里适合在更新之前访问现有的 DOM，比如手动移除已添加的事件监听器。

- **updated**: 由于数据更改导致的虚拟 DOM 重新渲染和打补丁，在这之后会调用该钩子。当这个钩子被调用时，组件 DOM 已经更新，所以现在可以执行依赖于 DOM 的操作。

- **beforeDestroy**: 在实例销毁之前调用。在这一步，实例仍然完全可用。

- **destroyed**: 在实例销毁之后调用。调用后，Vue 实例指示的所有东西都会解绑定，所有的事件监听器会被移除，所有的子实例也会被销毁。

### Vue 3 生命周期钩子：

在 Vue 3 中，生命周期钩子有了些许变化和重命名：

- **beforeCreate**: (在 Vue 3 中已经被移除)

- **created**: (在 Vue 3 中已经被移除)

- **beforeMount**: 在挂载之前被调用。

- **mounted**: 在挂载之后被调用。

- **beforeUpdate**: 在更新之前被调用。

- **updated**: 在更新之后被调用。

- **beforeUnmount**: 在卸载之前被调用（Vue 2 中为 `beforeDestroy`）。

- **unmounted**: 在卸载之后被调用（Vue 2 中为 `destroyed`）。

- **activated**: 被 `<keep-alive>` 缓存的组件激活时调用。

- **deactivated**: 被 `<keep-alive>` 缓存的组件停用时调用。

- **errorCaptured**: 当捕获一个来自子孙组件的错误时被调用。

为了适应组合式 API，Vue 3 还引入了 `setup` 函数，它是组合式 API 的入口点，相当于 2.x 版本中的 `beforeCreate` 和 `created` 钩子的结合。

在使用组合式 API 时，你可能会使用以下的 Composition API 生命周期钩子函数：

- `onBeforeMount`
- `onMounted`
- `onBeforeUpdate`
- `onUpdated`
- `onBeforeUnmount` (替代 `beforeDestroy`)
- `onUnmounted` (替代 `destroyed`)
- `onActivated`
- `onDeactivated`
- `onErrorCaptured`

这些函数提供了与选项式 API 相同的钩子函数功能，但它们可以在 `setup` 函数中直接使用。









---

创建一个新的Vue项目通常涉及使用Vue CLI（命令行工具）。在您准备创建一个新项目之前，请确保您已经安装了Node.js和npm（Node.js的包管理器）。

以下是使用Vue CLI创建一个新Vue项目的步骤：

1. **安装Vue CLI**（如果尚未安装）：

   ```sh
   npm install -g @vue/cli
   ```

   `-g` 参数表示全局安装，让 Vue CLI 在系统任何地方都可用。

2. **创建新项目**：

   ```sh
   vue create 你的项目名称
   ```

   例如：

   ```sh
   vue create my-vue-project
   ```

   这个命令会启动一个交互式的界面，让你选择一些配置选项，比如预设（默认配置、手动选择特性等）、Vue版本、添加的Vue插件等。

3. **进入项目目录**：

   ```sh
   cd my-vue-project
   ```

4. **启动开发服务器**：

   ```sh
   npm run serve
   ```

   这个命令将启动一个热重载的本地开发服务器。

5. **访问应用**：
   打开浏览器，输入 [http://localhost:8080](http://localhost:8080)（或者根据命令行输出的地址，可能因端口占用而有所不同）访问你的新Vue应用。

6. **后续开发**：
   之后，你可以开始编写你的Vue组件和应用逻辑。

7. **构建项目**：
   当你准备好将你的应用部署到生产环境时，可以使用以下命令来构建你的应用：

   ```sh
   npm run build
   ```

   这将创建一个`dist`文件夹，里面包含了用于生产环境的文件，你可以将这些文件部署到任何静态文件服务器上。

请根据自己的需求和喜好选择合适的配置。Vue CLI 提供的项目结构是一个很好的起点，并包含了一些最佳实践。











---

校验json  

https://www.bejson.com/