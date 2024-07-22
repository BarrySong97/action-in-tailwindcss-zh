# 快速开始

## 在开始之前

本小册不会说原理只会说怎么运用tailwind。

并且只需要你会使用npm，pnpm，yarn，以及看得懂文档，了解基础的js/css/react/vue知识即可。

## 一些准备

首先我们快速使用vite启动一个模板

```
pnpm create vite

```

打开[tailwind](https://tailwindcss.com/docs/guides/vite)
的文档，按照文档配置tailwind

接着使用vscode的同学，可以安装一个tailwind插件`Tailwind CSS IntelliSense`

在className里面写原子class的时候会有智能提示。

把鼠标放在原子class上面可以快速查看原子的css转换。

![img1](https://raw.githubusercontent.com/bradlc/vscode-tailwindcss/master/packages/vscode-tailwindcss/.github/banner.png)

![img2](https://raw.githubusercontent.com/bradlc/vscode-tailwindcss/master/packages/vscode-tailwindcss/.github/hover.png)

## 使用tailwind原子的几种方式

### 1. 直接使用设定好的原子

```jsx
<h1 className="text-3xl font-bold underline">Hello world!</h1>
```

### 2. 使用自定义数值原子

比如在上面代码里面的`3xl`,`bold`指的都是设定好的值（能符合大部分设计原则的数值）。

```css
.text-3xl {
  font-size: 1.875rem /* 30px */;
  line-height: 2.25rem /* 36px */;
}
.font-bold {
  font-weight: 700;
}
```

但是我们想要设定`font-size`为`27px`呢？当然设定一个诡异的数值不好，这里只是举个例子。
一般情况下，我们都会设置自定义颜色，高度宽度的需求。
我们有原子`w-3`，`h-3`，`text-white`这种。
![1721637498829.png](https://cdn-fusion.imgimg.cc/i/2024/2b1c94cea6e9ac04.png)
现在我们需要高度为`223px`，颜色为`#ECF5F7`

我们可以使用`原子名-[原子值]`的形式，如下

```jsx
<h1 className="h-[223px] text-3xl font-bold text-[#ECF5F7] underline">
  Hello world!
</h1>
```

### 3. 直接使用css

使用`[css代码]`的形式可以直接像写css一样写单条css语法。

```jsx
<h1 className="h-[223px] text-3xl font-bold underline [color:red]">
  Hello world!
</h1>
```

`[color:red]`直接转化为

```css
.\[color\:red\] {
  color: red;
}
```
