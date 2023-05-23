# husky

## 安装

pnpm add husky

安装完后package.json就会出现"prepare":"husky install"这时候我们执行下

pnpm prepare

执行完就会出现一个.husky文件

我们之所以配置husky就是为了以防小白没有去配置我们的eslint和stylelint的自动保存修改格式，或者遗漏一些文件的格式检测所以我们也需要保证我们的package.json中有完整的格式检测

eslint的检测配置命令

"lint":"eslint . --ext .vue,.js,.ts,.jsx,.tsx"

stylelint的检测配置命令

css版本 "lint:style": "stylelint **/*.{html,vue} --custom-syntax postcss-html"

less版本 "lint:less": "stylelint \"./**/*.{css,less,vue,html}\""

scss版本  "lint:less": "stylelint \"./**/*.{css,scss,vue,html}\""

配置完执行如下命令在.husky文件夹下面生成我们的pre-commit文件也就是git hook中commit之前的钩子

pnpm husky add .husky/pre-commit "pnpm lint && pnpm lint:style"

配置完后每次在我们git commit的时候都会去检测我们的代码规范是否符合eslint和stylelint