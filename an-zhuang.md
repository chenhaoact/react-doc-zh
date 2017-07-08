#安装

React是一项灵活的技术，它能被应用到一系列的项目中. 你可以用它创建新的应用，也可以不需要重写就能逐步地将它引入到已有的代码库中。

以下有三个场景，你可以根据你想要做的事选择不同的方式安装与实践：

## 尝试React

如果你仅仅有兴趣玩一下React，你可以使用CodePen。通过 [this Hello World example code](http://codepen.io/gaearon/pen/rrpgNB?editors=0010)开始尝试。你不需要安装任何东西；你可以仅仅修改下代码然后看它是否生效。

如果你喜欢用你自己的文本编辑器，你也可以<a href="https://facebook.github.io/react/downloads/single-file-example.html" download="hello.html">下载这个Html文件</a>，编辑它，并用你本地浏览器的文件系统打开。它需要短暂的时间进行代码转化，所以不要在生产环境下使用它。

如果你想要在整个应用中都使用React，有两种主流的方式进行React起步：使用 Create React App，或者把它添加到现有的应用中。


## 创建一个新的应用

[Create React App](http://github.com/facebookincubator/create-react-app) 是开始构建一个React单页应用最好的方式。它设置好你的开发环境以便你能使用最新的js特性，并提供了好的开发体验，还为生产环境优化了你的应用。

```bash
npm install -g create-react-app
create-react-app my-app

cd my-app
npm start
```

创建React引用不需要处理后端的逻辑或者数据库；仅仅创建一个前端的构建管道，因此你可以用你想用的任何后端技术。Create React App使用像Babel 和 webpack这样的构建工具，但他不需要任何的配置就能工作。

当你准备好部署到生产环境时，运用 `npm run build` 将会在你应用的`build` 目录下创建一个压缩打包优化过的代码。 你可以了解到更多Create React App的细节： [通过它的 README](https://github.com/facebookincubator/create-react-app#create-react-app-) 和 [User Guide](https://github.com/facebookincubator/create-react-app/blob/master/packages/react-scripts/template/README.md#table-of-contents).


## 添加 React 到一个已有的应用

你不需要为开始使用React重写你的应用。

我们推荐添加React为你应用的一小部分，像一个个人的插件，这样你就可以看它是否对你的用例运行良好。

React也 [可以被使用](https://facebook.github.io/react/docs/react-without-es6.html) 不需要构建管道，我们推荐设置它是为了让你的应用能生产效率更高。 一个典型的现代构建工作流包括：

* 一个 **包管理工具**，如 [Yarn](https://yarnpkg.com/) 或 [npm](https://www.npmjs.com/)。它能让你利用第三方库的巨大生态系统，并便捷的安装和更新它们。
* 一个 **打包工具**，如 [webpack](https://webpack.js.org/) 或 [Browserify](http://browserify.org/)。它能让你编写模块化的代码并把它们打包压缩以便优化加载时间。
* 一个 **编译工具**，如 [Babel](http://babeljs.io/)。 它可以允许你写新版的js代码并仍然可以在旧的浏览器中运行。

### 安装 React

>**注意：**
>
>一旦安装，我们就强烈建议设置 [生产构建流程](https://facebook.github.io/react/docs/optimizing-performance.html#use-the-production-build) 来确保你能在生产环境中使用最快版本的React。

我们推荐使用[Yarn](https://yarnpkg.com/) 或 [npm](https://www.npmjs.com/) 来管理前端依赖。如果你是包管理工具的新手，[Yarn的文档](https://yarnpkg.com/en/docs/getting-started) 会对你的起步有所帮助。

用Yarn安装React，运行：

```bash
yarn init
yarn add react react-dom
```

用npm安装React，运行：

```bash
npm init
npm install --save react react-dom
```

Yarn 和 npm 都从 [npm registry](http://npmjs.com/)下载包。

### 启用ES6 和 JSX

我们推荐使用 [Babel](http://babeljs.io/) 配合React 以便在你的js代码中支持 ES6 和 JSX. ES6 is a set of modern JavaScript features that make development easier, and JSX is an extension to the JavaScript language that works nicely with React.

The [Babel setup instructions](https://babeljs.io/docs/setup/) explain how to configure Babel in many different build environments. Make sure you install [`babel-preset-react`](http://babeljs.io/docs/plugins/preset-react/#basic-setup-with-the-cli-) and [`babel-preset-es2015`](http://babeljs.io/docs/plugins/preset-es2015/#basic-setup-with-the-cli-) and enable them in your [`.babelrc` configuration](http://babeljs.io/docs/usage/babelrc/), and you're good to go.

### Hello World with ES6 and JSX

We recommend using a bundler like [webpack](https://webpack.js.org/) or [Browserify](http://browserify.org/) so you can write modular code and bundle it together into small packages to optimize load time.

The smallest React example looks like this:

```js
import React from 'react';
import ReactDOM from 'react-dom';

ReactDOM.render(
  <h1>Hello, world!</h1>,
  document.getElementById('root')
);
```

This code renders into a DOM element with the id of `root` so you need `<div id="root"></div>` somewhere in your HTML file.

Similarly, you can render a React component inside a DOM element somewhere inside your existing app written with any other JavaScript UI library.

[Learn more about integrating React with existing code.](/react/docs/integrating-with-other-libraries.html#integrating-with-other-view-libraries)

### Development and Production Versions

By default, React includes many helpful warnings. These warnings are very useful in development.

**However, they make the development version of React larger and slower so you should use the production version when you deploy the app.**

Learn [how to tell if your website is serving the right version of React](/react/docs/optimizing-performance.html#use-the-production-build), and how to configure the production build process most efficiently:

* [Creating a Production Build with Create React App](/react/docs/optimizing-performance.html#create-react-app)
* [Creating a Production Build with Single-File Builds](/react/docs/optimizing-performance.html#single-file-builds)
* [Creating a Production Build with Brunch](/react/docs/optimizing-performance.html#brunch)
* [Creating a Production Build with Browserify](/react/docs/optimizing-performance.html#browserify)
* [Creating a Production Build with Rollup](/react/docs/optimizing-performance.html#rollup)
* [Creating a Production Build with webpack](/react/docs/optimizing-performance.html#webpack)

### Using a CDN

If you don't want to use npm to manage client packages, the `react` and `react-dom` npm packages also provide single-file distributions in `dist` folders, which are hosted on a CDN:

```html
<script src="https://unpkg.com/react@15/dist/react.js"></script>
<script src="https://unpkg.com/react-dom@15/dist/react-dom.js"></script>
```

The versions above are only meant for development, and are not suitable for production. Minified and optimized production versions of React are available at:

```html
<script src="https://unpkg.com/react@15/dist/react.min.js"></script>
<script src="https://unpkg.com/react-dom@15/dist/react-dom.min.js"></script>
```

To load a specific version of `react` and `react-dom`, replace `15` with the version number.

If you use Bower, React is available via the `react` package.