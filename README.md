# english.zuo11.com

## 初始化项目
使用vue-cli创建项目：[创建一个项目 | vue-cli](https://cli.vuejs.org/zh/guide/creating-a-project.html)
```bash
# 查看vue-cli版本
guoqzuo-mac:feclone kevin$ vue -V
@vue/cli 4.5.0

# 创建项目
vue create english.zuo11.com

# 配置选项如下
? Please pick a preset: Manually select features
? Check the features needed for your project: Choose Vue version, Babel, Router, Vuex, CSS Pre-processors, Linter
? Choose a version of Vue.js that you want to start the project with 2.x
? Use history mode for router? (Requires proper server setup for index fallback in production) Yes
? Pick a CSS pre-processor (PostCSS, Autoprefixer and CSS Modules are supported by default): Less
? Pick a linter / formatter config: Prettier
? Pick additional lint features: Lint on save
? Where do you prefer placing config for Babel, ESLint, etc.? In package.json
? Save this as a preset for future projects? (y/N) n
```

## 关联到github仓库
在github创建一个空的仓库，命名为 english.zuo11.com
```bash
git remote add origin git@github.com:zuoxiaobai/english.zuo11.com.git
git push -u origin master
```

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
