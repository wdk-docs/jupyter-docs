# Jupyter NodeJS

这是[Jupyter](http://github.com/ipython/ipython)的核心

在炎热的时候得到它！或查看[示例笔记本](http://nbviewer.ipython.org/gist/jaredly/404a36306fdee6a1737a)

## 预先要求

- IPython 3.x
- node
- ZeroMQ
- pkg-config

## 安装

```bash
git clone https://github.com/notablemind/jupyter-nodejs.git
cd jupyter-nodejs
mkdir -p ~/.ipython/kernels/nodejs/
npm install && node install.js
npm run build
npm run build-ext
jupyter console --kernel nodejs
```

And viola!

![image](https://cloud.githubusercontent.com/assets/112170/7268122/a33b186c-e882-11e4-8463-be00a6c90163.png)

Also, in the iPython notebook:

![image](https://cloud.githubusercontent.com/assets/112170/7268108/70cade4e-e882-11e4-95e7-8a7375b3b888.png)

## 支持的功能

- tab-completion (both for variables and **paths**)
- error reporting
- magics! The available extensions can be configured via `package/config.js`

## 安装

`node install.js [install-dir]` will install the `kernel.json` file that ipython looks for. The default is for linux machines, `~/.ipython/kernels/nodejs/`. You will have to specify an install dir for Mac and Windows (see [the docs](https://ipython.org/ipython-doc/dev/development/kernels.html#kernel-specs) for info about what that should be)

## BabelJS Magic for es6+ goodness

`%load_ext babel` and then

```javascript
%%babel
class Awesome {
  constructor() {
    console.log('yeah!')
  }
}
```

**Hovever:** `import ...` syntax _doesn't work_ because of [live bindings](https://github.com/ModuleLoader/es6-module-loader/wiki/Circular-References-&-Bindings#es6-circular-references--bindings) foo, so just use `require()` normally and all will be well.

## 通过[himera](https://github.com/fogus/himera)服务器进行 Clojurescript 编译

`%load_ext clojurescript http://himera-emh.herokuapp.com` and then

```clojure
%%clojurescript
(clojurey goodness)
```
