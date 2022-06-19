# Vue脚手架笔记

## 脚手架文件结构
```text
├── README.md   应用描述文件
├── babel.config.js babel配置文件
├── jsconfig.json
├── node_modules    模块依赖包目录
├── package-lock.json   包版本控制文件
├── package.json    应用包配置文件
├── public  静态资源目录
│   ├── favicon.ico 页面标签图标
│   └── index.html  主页面
├── src 源码目录
│   ├── App.vue 汇总所有组件
│   ├── assets  存放静态资源
│   ├── components  存放组件目录
│   └── index.js    主页面
└── vue.config.js   Vue核心配置文件
```

## 不同版本Vue的区别

`vue.js`与`vue.runtime.xxx.js`的区别：

1. `vue.js`是完整版的vue，包含`核心功能`+`模板解析器`；
2. `vue.runtime.xxx.js`是运行版的Vue，只包含`核心功能`，没有模板解析器；

> 因为vue.runtime.xxx.js没有模板解析器，所以不能使用template配置项，需要使用render函数接受收到的createElement函数去指定具体内容

```vue
new Vue({
  render: h => h(App),
}).$mount('#app')
```

## vue.config.js配置文件

> 使用`vue inspect > output.js`可以查看到Vue脚手架的默认配置；
>
> 使用`vue.config.js`可以对脚手架进行个性化定制

```vue
const { defineConfig } = require('@vue/cli-service')
module.exports = defineConfig({
  transpileDependencies: true,
  lintOnSave:false,  //关闭语法检查
  pages: {
    index: {
      entry: 'src/index.js'  // 入口文件
    }
  }
})
```

## 常用命令

```
# 会根据项目中的package.json文件自动下载项目所需的全部依赖
npm install
# 编译和运行Vue，可以运行时更新，用于开发Vue
npm run serve
# 针对生产环境进行编译和简化,打包构建成静态文件:html,css,javascript
npm run build
# 语法检查，修复错误的配置，基本不用
npm run lint
```

## ref属性

> ref属性别用来给元素或子组件注册引用信息（id的替代者）

ref应用在html标签上获取的是真实的DOM元素，应用在组件上获取的是组件的实例对象

- 给标签设置标识

```vue
<h2 ref="appTitle">App组件</h2>
```

- 获取`ref`

```
console.log('@',this.$refs.appTitle)
```

## props配置

> 让组件接收外部传来的数据

传递数据

```vue
<School name='北京大学' address='四道口职业技术学院'></School>
```

接收数据

- 普通接收

```vue
props: ['name','address']
```

- 限制接收

```vue
props: {
  name: {
    type: String,   // 类型
    required: true, // 是否必须
    default: '张三'  // 默认值
  },
    address: {
    type: String,   // 类型
    required: true // 是否必须
  }
}
```

## mixin(混入)

> 可以把多个组件共用的配置提取成一个混入对象

定义混入，创建`mixin.js`

```vue
export const mixin = {
    methods: {
        getName(){
            alert(this.name)
        }
    }
}
```

使用混入

```vue
# 导入mixin
import {mixins} from '../mixin'

# 局部混入
mixins:[mixin]
# 全局混入
Vue.mixin(mixin)
```

