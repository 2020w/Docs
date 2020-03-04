### 初始化vue项目
- 执行`npm install`，安装依赖包
- 建议安装"EditorConfig for VSCode"插件，保持编码风格统一，否则ESLint可能会在编码时报错
- 可执行`npm run serve`运行vue项目（要先运行node服务器）

### node服务器
- 此服务器用于模拟提供vue项目所需要的api和静态资源
- 执行`npm install`，安装依赖包
- 静态资源路径为：http://127.0.0.1:3000/images/ + 资源名
- api访问路径为：http://127.0.0.1:3000/api 返回一个json对象用于测试，可随时根据需要修改lib目录下的test.json字段来提供自己需要的数据
- 执行`npm start`启动服务器

### 任务划分
- 主页（可在Home.vue文件中预览划分的模块）,以下文件在/src/views/bussiness/home目录下
  1. About.vue
  2. Team.vue
  3. Service.vue
  4. Style.vue
  5. Contact.vue
  6. Footer.vue
- 产品页（待续。。。）
- 技术介绍页（待续。。。）

### 主要目标
- 将每个组件模板中需要动态展示的数据抽离出来，包括：
  - 静态资源url（如图片路径）以变量存储的形式放在vue实例的data域中，并修改路径为服务器资源地址（自行测试）
  - 需要动态显示的文本信息以变量存储的形式放在vue实例的data域中，文本数据需要通过ajax访问服务器api路径动态获取
  - 所有的ajax访问均通过axios来实现，axios已经引入，可通过this.$http获取
- 复用性较高的小型组件可单独开发，放置common文件夹中作全局引用
- 自行合理地对组件进行修改，去掉或修改不符合网站主题的部分（如广告区，视频区等）
- 自行准备需要向服务器获取的数据，包括：
  - 符合区块链、人体健康主题的图片放在服务器的静态资源目录public/images下
  - 关于团队介绍、产品介绍等信息暂时放在服务器的lib/test.json文件中，添加对应的字段即可
- 本次不再重构CSS代码
- 解决不了的问题先做记录
