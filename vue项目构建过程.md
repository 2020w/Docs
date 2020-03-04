## 门户网站构建过程（前端）
### 创建vue项目
1. 执行 `vue ui` ，以图形化界面方式创建vue项目
2. 手动配置项目：
   - 添加babel
   - 添加Router
   - Linter/Formatter（ESLint + standard config）
   - 使用配置文件
3. 点击创建项目

### 项目初始化
1. 执行 `npm install` 安装依赖包
2. 创建vue.config.js文件，用于配置webpack
3. 配置.gitignore文件，禁止上传node_modules目录下的文件
4. 配置.eslintrc.js文件，规范编码风格

### 项目重构
1. 获取前端模板文件
2. 将静态资源放置在/src/assets目录下
3. main.js:
   - 导入全局样式表
   - 导入bootstrap、animate
   - 导入第三方脚本
   - 导入初始化脚本
4. 配置插件
   - jquery
     - 执行`npm install jquery@1.11.0`(版本不一致会出现问题)
     - 配置vue.config.js文件，通过`webpack.ProviderPlugin`全局引入jquery
   - imports-load
     - 执行`npm install imports-loader`安装imports-load
     - 配置vue.config.js文件，将window对象导入第三方脚本中以解决Moderniz插件引用出错的问题
   - axios
     - 执行`npm install axios`
     - 在main.js中引入axios，并挂载到Vue原型对象上

### 组件划分
  - 原则：
    - 多页面 -> 单页面
    - 单页面 -> 多组件
  - 组件归类：
    - views/bussiness: 存放每个页面的业务级组件，一般不可复用
    - views/common：存放复用性较高的小型组件
  - 文档结构：
    - 每个页面（包括主页、产品页、技术页等）涉及的组件都有对应的存放目录，例如home页面对应于views/bussiness/home