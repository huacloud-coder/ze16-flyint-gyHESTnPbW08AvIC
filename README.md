[合集 \- 2024/08(31\)](https://github.com)[1\.使用 useState 管理响应式状态08\-01](https://github.com/Amd794/p/18336394)[2\.使用 $fetch 进行 HTTP 请求08\-02](https://github.com/Amd794/p/18338013)[3\.使用 abortNavigation 阻止导航08\-03](https://github.com/Amd794/p/18340086)[4\.使用 addRouteMiddleware 动态添加中间08\-04](https://github.com/Amd794/p/18341511)[5\.使用 clearError 清除已处理的错误08\-05](https://github.com/Amd794/p/18342927)[6\.清除 Nuxt 数据缓存：clearNuxtData08\-06](https://github.com/Amd794/p/18344624)[7\.清除 Nuxt 状态缓存：clearNuxtState08\-07](https://github.com/Amd794/p/18346580)[8\.使用 createError 创建错误对象的详细指南08\-08](https://github.com/Amd794/p/18348424)[9\.使用 defineNuxtComponent\`定义 Vue 组件08\-09](https://github.com/Amd794/p/18350231)[10\.使用 defineNuxtRouteMiddleware 创建路由中间件08\-10](https://github.com/Amd794/p/18351993)[11\.掌握 Nuxt 3 的页面元数据：使用 definePageMeta 进行自定义配置08\-11](https://github.com/Amd794/p/18353145)[12\.使用 Nuxt 3 的 defineRouteRules 进行页面级别的混合渲染08\-12](https://github.com/Amd794/p/18354387)[13\.使用 navigateTo 实现灵活的路由导航08\-13](https://github.com/Amd794/p/18356264)[14\.使用 onBeforeRouteLeave 组合式函数提升应用的用户体验08\-14](https://github.com/Amd794/p/18358448)[15\.使用 onBeforeRouteUpdate 组合式函数提升应用的用户体验08\-15](https://github.com/Amd794/p/18360622)[16\.使用 onNuxtReady 进行异步初始化08\-16](https://github.com/Amd794/p/18362628)[17\.使用 prefetchComponents 进行组件预取08\-17](https://github.com/Amd794/p/18364201)[18\.使用 preloadComponents 进行组件预加载08\-18](https://github.com/Amd794/p/18365440)[19\.使用 preloadRouteComponents 提升 Nuxt 应用的性能08\-19](https://github.com/Amd794/p/18367070)[20\.使用 prerenderRoutes 进行预渲染路由08\-20](https://github.com/Amd794/p/18369184)[21\.使用 refreshNuxtData 刷新 Nuxt应用 中的数据08\-21](https://github.com/Amd794/p/18371979)[22\.使用 reloadNuxtApp 强制刷新 Nuxt 应用08\-23](https://github.com/Amd794/p/18375676)[23\.如何在 Nuxt 中动态设置页面布局08\-24](https://github.com/Amd794/p/18377415)[24\.使用 setResponseStatus 函数设置响应状态码08\-25](https://github.com/Amd794/p/18378745)[25\.使用 Nuxt 的 showError 显示全屏错误页面08\-26](https://github.com/Amd794/p/18379993)[26\.使用 updateAppConfig 更新 Nuxt 应用配置08\-27](https://github.com/Amd794/p/18382205)[27\.使用 nuxi add 快速创建 Nuxt 应用组件08\-28](https://github.com/Amd794/p/18384327)[28\.使用 nuxi analyze 命令分析 Nuxt 应用的生产包08\-29](https://github.com/Amd794/p/18386532)[29\.使用 nuxi build 命令构建你的 Nuxt 应用程序08\-30](https://github.com/Amd794/p/18388346)30\.使用 nuxi build\-module 命令构建 Nuxt 模块08\-31[31\.使用 nuxi clean 命令清理 Nuxt 项目09\-01](https://github.com/Amd794/p/18391134)收起


---


title: 使用 nuxi build\-module 命令构建 Nuxt 模块
date: 2024/8/31
updated: 2024/8/31
author:  [cmdragon](https://github.com) 


excerpt:
nuxi build\-module 命令是构建 Nuxt 模块的核心工具，它将你的模块打包成适合生产环境的格式。通过使用 \-\-stub 选项，你可以在开发过程中加快模块构建速度，但在发布之前最好进行最终构建以确保模块的生产质量。理解和掌握这些选项将帮助你更好地控制模块的构建过程，并确保模块能够顺利地发布和分发。


categories:


* 前端开发


tags:


* Nuxt模块
* 构建工具
* nuxi命令
* 生产构建
* 模块打包
* TypeScript支持
* ESM支持




---


[![](https://img2024.cnblogs.com/blog/1546022/202408/1546022-20240831130624756-2043445465.png)](https://img2024.cnblogs.com/blog/1546022/202408/1546022-20240831130624756-2043445465.png)
[![](https://img2024.cnblogs.com/blog/1546022/202408/1546022-20240831130630421-244188240.png)](https://img2024.cnblogs.com/blog/1546022/202408/1546022-20240831130630421-244188240.png)


扫描[二维码](https://github.com)关注或者微信搜一搜：`编程智域 前端至全栈交流与成长`


如果你正在开发一个 Nuxt 模块并希望在发布之前将其构建为生产版本，那么 `nuxi build-module` 命令将是你不可或缺的工具。


## 什么是 `nuxi build-module`？


`nuxi build-module` 命令用于构建你的 Nuxt 模块。在发布模块之前，运行这个命令会生成一个名为 `dist` 的目录，该目录包含了构建后的模块文件，准备好用于发布和分发。这个命令使用了 `@nuxt/module-builder` 工具，它可以自动生成符合最新模块规范的构建配置，并支持 TypeScript 和 ESM（ECMAScript 模块）。


### 基本用法



```
npx nuxi build-module [--stub] [rootDir]

```

### 参数说明


* **rootDir**：要打包的模块的根目录，默认为当前目录 (`.`)。如果你的模块位于不同的目录，可以指定其他路径。
* **\-\-stub**：使用 `jiti` 对你的模块进行存根处理。这个选项主要用于开发目的，可以加快开发过程，但可能会影响模块的生产构建。


## 如何使用 `nuxi build-module` 命令


### 1\. 准备你的 Nuxt 模块


在构建你的模块之前，需要确保模块已经正确创建和配置。如果你还没有创建模块，可以按照以下步骤创建一个简单的模块：


1. **创建模块目录**：



```
mkdir my-nuxt-module
cd my-nuxt-module

```
2. **初始化 npm 项目**：



```
npm init -y

```
3. **安装必要的依赖**：



```
npm install nuxt @nuxt/module-builder

```
4. **创建模块文件**：


在模块目录中，创建一个 `index.js` 文件，写入你的模块代码。例如：



```
export default function MyModule(moduleOptions) {
  this.addPlugin({
    src: require.resolve('./plugin.js'),
    fileName: 'my-module.js',
    options: moduleOptions
  })
}

```

然后，创建一个 `plugin.js` 文件，例如：



```
export default function ({ app }, inject) {
  // 在这里添加你的插件逻辑
  inject('myModule', 'Hello from my module!')
}

```


### 2\. 运行 `nuxi build-module` 命令


在你的模块目录中，运行以下命令来构建模块：



```
npx nuxi build-module

```

这个命令将会生成一个名为 `dist` 的目录，其中包含构建后的模块文件。这个 `dist` 目录准备好用于发布和分发。


### 3\. 使用 `--stub` 选项


如果你正在开发模块，并希望使用 `jiti` 对模块进行存根处理，以加快开发过程，可以使用 `--stub` 选项：



```
npx nuxi build-module --stub

```

请注意，`--stub` 选项主要用于开发目的，它可以加快模块的开发过程，但在发布之前最好去掉这个选项进行最终构建。


## 示例


假设你已经创建了一个名为 `my-nuxt-module` 的模块，并希望构建这个模块。以下是如何使用 `nuxi build-module` 命令的示例：


1. **基本构建**：


在 `my-nuxt-module` 目录中运行以下命令：



```
npx nuxi build-module

```

这个命令会在 `my-nuxt-module` 目录下生成一个 `dist` 目录，其中包含构建后的模块文件，准备好用于发布。
2. **使用 `--stub` 选项**：


如果你正在开发模块并希望使用存根处理来加快开发速度，可以运行：



```
npx nuxi build-module --stub

```

这会使用 `jiti` 对模块进行存根处理，适合开发期间使用。


## 总结


nuxi build\-module 命令是构建 Nuxt 模块的核心工具，它将你的模块打包成适合生产环境的格式。通过使用 \-\-stub 选项，你可以在开发过程中加快模块构建速度，但在发布之前最好进行最终构建以确保模块的生产质量。理解和掌握这些选项将帮助你更好地控制模块的构建过程，并确保模块能够顺利地发布和分发。


余下文章内容请点击跳转至 个人博客页面 或者 扫码关注或者微信搜一搜：`编程智域 前端至全栈交流与成长`，阅读完整的文章：[使用 nuxi build\-module 命令构建 Nuxt 模块 \| cmdragon's Blog](https://github.com):[MeoMiao 萌喵加速](https://biqumo.org)


## 往期文章归档：


* [使用 nuxi build 命令构建你的 Nuxt 应用程序 \| cmdragon's Blog](https://github.com)
* [使用 nuxi analyze 命令分析 Nuxt 应用的生产包 \| cmdragon's Blog](https://github.com)
* [使用 nuxi add 快速创建 Nuxt 应用组件 \| cmdragon's Blog](https://github.com)
* [使用 updateAppConfig 更新 Nuxt 应用配置 \| cmdragon's Blog](https://github.com)
* [使用 Nuxt 的 showError 显示全屏错误页面 \| cmdragon's Blog](https://github.com)
* [使用 setResponseStatus 函数设置响应状态码 \| cmdragon's Blog](https://github.com)
* [如何在 Nuxt 中动态设置页面布局 \| cmdragon's Blog](https://github.com)
* [使用 reloadNuxtApp 强制刷新 Nuxt 应用 \| cmdragon's Blog](https://github.com)
* [使用 refreshNuxtData 刷新 Nuxt应用 中的数据 \| cmdragon's Blog](https://github.com)
* [使用 prerenderRoutes 进行预渲染路由 \| cmdragon's Blog](https://github.com)
* [使用 preloadRouteComponents 提升 Nuxt 应用的性能 \| cmdragon's Blog](https://github.com)
* [使用 preloadComponents 进行组件预加载 \| cmdragon's Blog](https://github.com)
* [使用 prefetchComponents 进行组件预取 \| cmdragon's Blog](https://github.com)
* [使用 onNuxtReady 进行异步初始化 \| cmdragon's Blog](https://github.com)
* [使用 onBeforeRouteUpdate 组合式函数提升应用的用户体验 \| cmdragon's Blog](https://github.com)
* [使用 onBeforeRouteLeave 组合式函数提升应用的用户体验 \| cmdragon's Blog](https://github.com)
* [使用 navigateTo 实现灵活的路由导航 \| cmdragon's Blog](https://github.com)
* [使用 Nuxt 3 的 defineRouteRules 进行页面级别的混合渲染 \| cmdragon's Blog](https://github.com)
* [掌握 Nuxt 3 的页面元数据：使用 definePageMeta 进行自定义配置 \| cmdragon's Blog](https://github.com)
* [使用 defineNuxtRouteMiddleware 创建路由中间件 \| cmdragon's Blog](https://github.com)
* 


  * [什么是 nuxi build\-module？](#%E4%BB%80%E4%B9%88%E6%98%AF-nuxi-build-module)
* [基本用法](#%E5%9F%BA%E6%9C%AC%E7%94%A8%E6%B3%95)
* [参数说明](#%E5%8F%82%E6%95%B0%E8%AF%B4%E6%98%8E)
* [如何使用 nuxi build\-module 命令](#%E5%A6%82%E4%BD%95%E4%BD%BF%E7%94%A8-nuxi-build-module-%E5%91%BD%E4%BB%A4)
* [1\. 准备你的 Nuxt 模块](#tid-bzGzYR)
* [2\. 运行 nuxi build\-module 命令](#tid-aKFeSd)
* [3\. 使用 \-\-stub 选项](#tid-Ekb7QB)
* [示例](#%E7%A4%BA%E4%BE%8B)
* [总结](#%E6%80%BB%E7%BB%93)
* [往期文章归档：](#%E5%BE%80%E6%9C%9F%E6%96%87%E7%AB%A0%E5%BD%92%E6%A1%A3)

   \_\_EOF\_\_

   ![](https://github.com/Amd794)Amd794  - **本文链接：** [https://github.com/Amd794/p/18390166](https://github.com)
 - **关于博主：** 评论和私信会在第一时间回复。或者[直接私信](https://github.com)我。
 - **版权声明：** 本博客所有文章除特别声明外，均采用 [BY\-NC\-SA](https://github.com "BY-NC-SA") 许可协议。转载请注明出处！
 - **声援博主：** 如果您觉得文章对您有帮助，可以点击文章右下角**【[推荐](javascript:void(0);)】**一下。
     
