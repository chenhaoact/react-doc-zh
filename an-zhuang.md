#安装

React是一项灵活的技术，它能被应用到一系列的项目中. 你可以用它创建新的应用，也可以不需要重写就能逐步地将它引入到已有的代码库中。

以下有三个场景，你可以根据你想要做的事选择不同的方式安装与实践：

## 尝试React

如果你仅仅有兴趣玩一下React，你可以使用CodePen。通过 [this Hello World example code](http://codepen.io/gaearon/pen/rrpgNB?editors=0010)开始尝试。你不需要安装任何东西；你可以仅仅修改下代码然后看它是否生效。

如果你喜欢用你自己的文本编辑器，你也可以<a href="https://facebook.github.io/react/downloads/single-file-example.html" download="hello.html">下载这个Html文件</a>，编辑它，并用你本地浏览器的文件系统打开。它需要短暂的时间进行代码转化，所以不要在生产环境下使用它。

如果你想要在整个应用中都使用React，有两种主流的方式进行React起步：使用 Create React App，或者把它添加到现有的应用中。


## 创建一个新的应用

[Create React App](http://github.com/facebookincubator/create-react-app) 是开始构建一个React单页应用最好的方式。它设置好你了开发环境以便你能使用最新的js特性，提供了好的开发体验 provides a nice developer experience, and optimizes your app for production.

```bash
npm install -g create-react-app
create-react-app my-app

cd my-app
npm start
```

Create React App doesn't handle backend logic or databases; it just creates a frontend build pipeline, so you can use it with any backend you want. It uses build tools like Babel and webpack under the hood, but works with zero configuration.

When you're ready to deploy to production, running `npm run build` will create an optimized build of your app in the `build` folder. You can learn more about Create React App [from its README](https://github.com/facebookincubator/create-react-app#create-react-app-) and the [User Guide](https://github.com/facebookincubator/create-react-app/blob/master/packages/react-scripts/template/README.md#table-of-contents).

<block id="existingapptab" role="tabpanel" class="existingapp" />

## Adding React to an Existing Application

You don't need to rewrite your app to start using React.

We recommend adding React to a small part of your application, such as an individual widget, so you can see if it works well for your use case.

While React [can be used](/react/docs/react-without-es6.html) without a build pipeline, we recommend setting it up so you can be more productive. A modern build pipeline typically consists of:

* A **package manager**, such as [Yarn](https://yarnpkg.com/) or [npm](https://www.npmjs.com/). It lets you take advantage of a vast ecosystem of third-party packages, and easily install or update them.
* A **bundler**, such as [webpack](https://webpack.js.org/) or [Browserify](http://browserify.org/). It lets you write modular code and bundle it together into small packages to optimize load time.
* A **compiler** such as [Babel](http://babeljs.io/). It lets you write modern JavaScript code that still works in older browsers.

### Installing React

>**Note:**
>
>Once installed, we strongly recommend setting up a [production build process](/react/docs/optimizing-performance.html#use-the-production-build) to ensure you're using the fast version of React in production.

We recommend using [Yarn](https://yarnpkg.com/) or [npm](https://www.npmjs.com/) for managing front-end dependencies. If you're new to package managers, the [Yarn documentation](https://yarnpkg.com/en/docs/getting-started) is a good place to get started.

To install React with Yarn, run:

```bash
yarn init
yarn add react react-dom
```

To install React with npm, run:

```bash
npm init
npm install --save react react-dom
```

Both Yarn and npm download packages from the [npm registry](http://npmjs.com/).

### Enabling ES6 and JSX

We recommend using React with [Babel](http://babeljs.io/) to let you use ES6 and JSX in your JavaScript code. ES6 is a set of modern JavaScript features that make development easier, and JSX is an extension to the JavaScript language that works nicely with React.

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

<script>
/**
 * The code below is based on a snippet from React Native Getting Started page.
 */

// Convert <div>...<span><block /></span>...</div>
// Into <div>...<block />...</div>
var blocks = document.getElementsByTagName('block');
for (var i = 0; i < blocks.length; ++i) {
  var block = blocks[i];
  var span = blocks[i].parentNode;
  var container = span.parentNode;
  container.insertBefore(block, span);
  container.removeChild(span);
}
// Convert <div>...<block />content<block />...</div>
// Into <div>...<block>content</block><block />...</div>
blocks = document.getElementsByTagName('block');
for (var i = 0; i < blocks.length; ++i) {
  var block = blocks[i];
  while (block.nextSibling && block.nextSibling.tagName !== 'BLOCK') {
    block.appendChild(block.nextSibling);
  }
}

function setSelected(value){
  var tabs = document.querySelectorAll('li[role="tab"]');
  for (var i = 0; i < tabs.length; ++i) {
    var tab = tabs[i];
    if (tab.className === 'button-' + value) {
      tabs[i].setAttribute('aria-selected', 'true');
      tabs[i].setAttribute('tabindex', '0');
    } else {
      tabs[i].setAttribute('aria-selected', 'false');
      tabs[i].setAttribute('tabindex', '-1');
    }
  }
}

function keyToggle(e, value, prevTab, nextTab){
  if (e.keyCode === 37) {
    document.getElementById(prevTab).focus();
    display('target', prevTab);
  }
  if (e.keyCode === 39) {
    document.getElementById(nextTab).focus();
    display('target', nextTab);
  }
}

function display(type, value) {
  setSelected(value);
  var container = document.getElementsByTagName('block')[0].parentNode;
  container.className = 'display-' + type + '-' + value + ' ' +
    container.className.replace(RegExp('display-' + type + '-[a-z]+ ?'), '');
}

// If we are coming to the page with a hash in it (i.e. from a search, for example), try to get
// us as close as possible to the correct platform and dev os using the hashtag and block walk up.
var foundHash = false;
if (window.location.hash !== '' && window.location.hash !== 'content') { // content is default
  // Hash links are added a bit later so we wait for them.
  window.addEventListener('DOMContentLoaded', selectTabForHashLink);
}

function selectTabForHashLink() {
  var hashLinks = document.querySelectorAll('a.hash-link');
  for (var i = 0; i < hashLinks.length && !foundHash; ++i) {
    if (hashLinks[i].hash === window.location.hash) {
      var parent = hashLinks[i].parentElement;
      while (parent) {
        if (parent.tagName === 'BLOCK') {
          var target = null;
          if (parent.className.indexOf('fiddle') > -1) {
            target = 'fiddle';
          } else if (parent.className.indexOf('newapp') > -1) {
            target = 'newapp';
          } else if (parent.className.indexOf('existingapp') > -1) {
            target = 'existingapp';
          } else {
            break; // assume we don't have anything.
          }
          display('target', target);
          foundHash = true;
          break;
        }
        parent = parent.parentElement;
      }
    }
  }
}
</script>
