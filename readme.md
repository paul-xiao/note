## install package

- github download packages --> mv /home/paul.xiao/.config/sublime-text-3/Packages/


## nginx

- sudo systemctl start nginx
- root directory :usr/share/nginx/html
- sudo ./nginx -t


## setup local dev enviroment

- 

## dojo
- declare
- engine
- this.inherited(arguments) 

```bash
  Superclass constructors are always called automatically, 
  and always before the subclass constructor. This convention 
  reduces boilerplate in 90% of cases. If it doesn’t fit your 
  needs see Manual Constructor Chaining below. For all other 
  methods, use this.inherited(arguments) to call the superclass method of the same name.



  Because both methods are critical to the templating process, 
  if you override either of these methods in your custom code — 
  make sure that you include a call to the parent version by adding 
  this.inherited(arguments) in your overridden method. See the 
  Understanding _WidgetBase Tutorial for more information on the widget lifecycle.


```
- templateString        //    a string representing the HTML of the template
- Lifecycle
  - 



## nls  --> National Language Support


## work precess


## git 


- git config --list
- git checkout -b branchname   //J265 
- git commit refs #AGN-265 comments
- git push origin J265
- merge request in gitlab
- git pull  //update
- git checkout dev
- git merge J265
- git push

- git stash
- git stash list
- git stash apply
- git stash drop
- git commit --amend
- git reset --hard COMMIT

- update branch
  - git branch --set-upstream-to=origin/master J323  // tracking information
  - git pull

```bash

#Rename your local branch.
#If you are on the branch you want to rename:

git branch -m new-name

#If you are on a different branch:

git branch -m old-name new-name

# Delete the old-name remote branch and push the new-name local branch.

git push origin :old-name new-name

#Reset the upstream branch for the new-name local branch.
#Switch to the branch and then:

git push origin -u new-name

```

## vue 

```java

- this.$store.dispatch('GET_USER_INFO')  // call actions

- how to put loading bar in each route  //api.js

- components html style    // outo convert to a-b , binding to tpl name

- mapGetters
 - mapGetters 辅助函数仅仅是将 store 中的 getter 映射到局部计算属性：

- vue-i18n
 - $t('upload.create_tp')

- Object.assign函数的使用
 - 使用该函数我们可以快速的复制一个或者多个对象到目标对象中

> 拼接字符串 :ref="`contact_key_${key}`"  

> $event 来获取到组件内部传递出来的第一个参数

```
#### vue-cli
```bash
# install
sudo npm install -g @vue/cli
vue --version

# crate 
vue create

```
## npm
 - npm config list
 - npm config set prefix '/home/paul.xiao/npm_global'
 - export PATH=$PATH:/home/paul.xiao/npm_global/bin/  


## notes
 - encodeURIComponent 




## tar.gz和tar.bz2解压命令

```bash
#解压tar.gz命令是
tar -zxvf xx.tar.gz
#解压tar.bz2的命令是
tar -jxvf xx.tar.bz2

```


## [ES6](https://www.w3schools.com/js/js_es6.asp)
> let,const
> Array.find()
  - The find() method returns the value of the first array element that passes a test function.

> New Global Methods
  - isFinite()
  - isNaN()

> Arrow Functions

```c

// ES5
var x = function(x, y) {
   return x * y;
}

// ES6
const x = (x, y) => x * y;


``` 


## alsamixer 

## mongoDB 
> [installation](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-red-hat/)
- Usage
  - service mongod status | start | stop


## web hacks
> image 



## docker

> install 

```



```



## node js package usage
> nodejs authentication
- passport.js
- jwt
- bcrypt

#### [cross-env](https://www.npmjs.com/package/cross-env)
> Run scripts that set and use environment variables across platforms
```bash
# package.json
{
  "scripts": {
    "build": "cross-env NODE_ENV=production webpack --config build/webpack.config.js"
  }
}
```
#### [nodemon](https://github.com/remy/nodemon#nodemon)
> nodemon is a tool that helps develop node.js based applications by automatically restarting the node application when file changes in the directory are detected.

```bash

# cmd
nodemon --inspect

# nodemon.json
{
  "verbose": true,
  "ignore": ["*.test.js", "fixtures/*"],
  "execMap": {
    "rb": "ruby",
    "pde": "processing --sketch={{pwd}} --run"
  }
}

```


#### nodejs-dashborad
> Determine in realtime what's happening inside your node process from the terminal. No need to instrument code to get the deets. Also splits stderr/stdout to help spot errors sooner.

```
# simply require in dev.index.js
require("nodejs-dashboard");
require("./index");

# launch
nodejs-dashboard node dev.index.js

# node -r usage
-r, --require   module to preload (option can be repeated)

# launch with node -r
nodejs-dashboard -- node -r nodejs-dashboard index.js

```

#### node-drawille
> drawing in terminal with unicode braille characters


#### webpack-dev-middleware
> An express-style development middleware for use with webpack bundles and allows for serving of the files emitted from webpack. This should be used for development only.

#### helmet  
> Helmet helps you secure your Express apps by setting various HTTP headers



## run time config

#### jshint
> JSHint, a tool that helps to detect errors and potential
  problems in your JavaScript code.
```
#  config es6 in .jshintrc

{
	"node": true,
	"sub": true,
	"esversion": 6, //specify the ECMAScript version
	"globals": {
		"require": true,
		"module": true
	}
}

# 自动检查代码

```  

#### chalk
> Terminal string styling

#### pug
> Pug is a high performance template engine heavily influenced by Haml and implemented with JavaScript for Node.js and browsers
```pug
doctype html
html(lang="en")
  head
    title= pageTitle
    script(type='text/javascript').
      if (foo) bar(1 + 5)
  body
    h1 Pug - node template engine
    #container.col
      if youAreUsingPug
        p You are amazing
      else
        p Get on it!
      p.
        Pug is a terse and simple templating language with a
        strong focus on performance and powerful features.
```















































-------------------------------------------------------

## markdown useage
# 锚点
# 一级标题
## 二级标题
#### 三级标题
##### 四级标题
###### 五级标题
######## 六级标题
# 引用
> 这是第一级引用。
>
> > 这是第二级引用。
>
> 现在回到第一级引用。

# 有序列表：使用数字接着一个英文句点
1. Red
2. Green
3. Blue

# 无序列表：使用星号、加号或是减号作为列表标记
- Red
- Green
- Blue
- [ ] 不勾选
- [x] 勾选


# codes

```ruby
require 'redcarpet'
markdown = Redcarpet.new("Hello World!")
puts markdown.to_html
```
# 强调
*Coding，让开发更简单*
_Coding，让开发更简单_

# 自动链接
[超强大的云开发平台Coding](http://coding.net)

# 表格
First Header | Second Header | Third Header
------------ | ------------- | ------------
Content Cell | Content Cell  | Content Cell
Content Cell | Content Cell  | Content 

# 分割线
这是分隔线上部分内容
---
这是分隔线上部分内容

# 图片
- Markdown 使用了类似链接的语法来插入图片, 包含两种形式: 内联 和 引用.
- 内联图片语法如下:
![Alt text](/path/to/img.jpg)
或
![Alt text](/path/to/img.jpg "Optional title")

- 引用图片语法如下

[id]: url/to/image "Optional title attribute"
![Alt text][id]

# 流程图

```graph
graph TD;
    A-->B;
    A-->C;
    B-->D;
    C-->E;
    E-->F;
    D-->F;
    F-->G;
```
# 时序图

```graph
sequenceDiagram
    participant Alice
    participant Bob
    Alice->John: Hello John, how are you?
    loop Healthcheck
        John->John: Fight against hypochondria
    end
    Note right of John: Rational thoughts 
prevail...
    John-->Alice: Great!
    John->Bob: How about you?
    Bob-->John: Jolly good!
```
# 甘特图

```graph
gantt
        dateFormat  YYYY-MM-DD
        title Adding GANTT diagram functionality to mermaid
        section A section
        Completed task            :done,    des1, 2014-01-06,2014-01-08
        Active task               :active,  des2, 2014-01-09, 3d
        Future task               :         des3, after des2, 5d
        Future task2               :         des4, after des3, 5d
        section Critical tasks
        Completed task in the critical line :crit, done, 2014-01-06,24h
        Implement parser and jison          :crit, done, after des1, 2d
        Create tests for parser             :crit, active, 3d
        Future task in critical line        :crit, 5d
        Create tests for renderer           :2d
        Add to mermaid                      :1d
```

