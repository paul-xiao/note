# Daily Notes


## Table of content
- [Linux](#linux)
- [Nginx](#nginx)
- [Tools](#tools)
  - [Vscode](#vscode)
- [Git](#git-usages)
- [Node](#node)
  - [Node Install](#node-install)
  - [Node Packages](#node-packages)
- [Vue](#vue)
  - [Vue Cli](#vue-cli)
  - [Vue Next](#vue-next)
- [ES6](#es6)
- [TypeScript](#typescript)
- [MongoDB](#mongodb)
- [Web Hacks](#web-hacks)
- [Docker](#docker)
- [React Native](#react-native)

--------------
### Linux

#### change CentOs 7 GUI to Mate-desktop

```bash
# install
$ sudo yum install -y epel-release
$ sudo yum groupinstall -y "MATE Desktop"
$ sudo reboot

# remove(if needed)
$ sudo yum groupremove -y "MATE Desktop"
$ sudo yum autoremove -y

# switch mate themes
1.  download themes here: https://mate-desktop.org/themes/
2.  put download file at : ~/.themes
3.  then you can find it in : System/Preference/Look and Feel/Apperance/theme
4.  download icons here: https://www.mate-look.org/s/Mate/browse/cat/132/ord/rating/
5.  put download file at : ~/.local/share/icons
6.  then go to : System/Preference/Look and Feel/Apperance/theme, click customize
7.  select icons
 
````
### Nginx

- sudo systemctl start nginx
- root directory :usr/share/nginx/html
- sudo ./nginx -t

### Tools

#### Vscode
- Optimize
> Visual Studio Code is unable to watch for file changes in this large workspace" (error ENOSPC)

```sh
# check max_user_watches
cat /proc/sys/fs/inotify/max_user_watches

# edit
sudo vi /etc/sysctl.conf

# add line below
fs.inotify.max_user_watches=524288

# effect
sudo sysctl -p
```


- Settings
  - user settings

```js
{
  // other settings
  // formatting using eslint
  // let editor format using prettier for all other files
  "editor.formatOnSave": true,
  // disable editor formatting, so eslint can handle it
  "[javascript]": {
    "editor.formatOnSave": false,
  },
  // available through eslint plugin in vscode
  "eslint.autoFixOnSave": true,
  "eslint.alwaysShowStatus": true,
}
```
  - workspace settings
```sh

touch .vscode/settings.json

```
- Extensions
  - [ESlint setup in react-native](https://medium.com/@deadcoder0904/eslint-setup-in-react-native-using-vscode-c3122a1da9c7)
  ```js
   // install 
   npm i -g eslint
   // init eslint
  ./node_modules/.bin/eslint --init

  ```
- fix on save

#### proxychains-ng

```sh
# source 
git clone https://github.com/rofl0r/proxychains-ng

# configure
./configure --prefix=/usr --sysconfdir=/etc
make
make install
make install-config
```

#### iptables

```sh

# check iptables

sudo iptables -L 

# allow specific ip/port
iptables -I INPUT -p tcp -s 192.168.196.131 -j ACCEPT


```


### Git Usages

```bash
# check config
git config --list

# set global user info 
git config --global user.email
git config --global user.name

# stash
git stash
git stash list
git stash apply
git stash drop

# reset commit
git commit --amend
git reset --hard COMMIT

# update branch
git branch --set-upstream-to=origin/master J323  // tracking information
git pull
#Rename your local branch.
#If you are on the branch you want to rename:

git branch -m new-name

#If you are on a different branch:

git branch -m old-name new-name

# Delete the old-name remote branch and push the new-name local branch.

git push origin :old-name new-name

# delete remote branch

git push origin --delete feature/login

#Reset the upstream branch for the new-name local branch.
#Switch to the branch and then:

git push origin -u new-name

# update git version centos 7

$ sudo yum install https://centos7.iuscommunity.org/ius-release.rpm
$ sudo yum erase git
$ sudo yum install epel-release 
$ sudo yum install git2u

```

### Node

#### Node Install
```SH
# CentOS 7
# node 12 LTS
sudo yum -y update
curl -sL https://rpm.nodesource.com/setup_12.x | sudo bash -
sudo yum clean all && sudo yum makecache fast
sudo yum install -y gcc-c++ make
sudo yum install -y nodejs
node -v
npm -v
# npm config
npm config list
npm config set prefix '~/.npm_global'
export PATH=$PATH:/home/paul.xiao/Workspace/.npm_global/bin/

```

#### Node Packages
> nodejs authentication
- passport.js
- jwt
- bcrypt

##### [cross-env](https://www.npmjs.com/package/cross-env)
> Run scripts that set and use environment variables across platforms
```bash
# package.json
{
  "scripts": {
    "build": "cross-env NODE_ENV=production webpack --config build/webpack.config.js"
  }
}
```
##### [nodemon](https://github.com/remy/nodemon#nodemon)
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


##### nodejs-dashborad
> Determine in realtime what's happening inside your node process from the terminal. No need to instrument code to get the deets. Also splits stderr/stdout to help spot errors sooner.

```bash
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

##### node-drawille
> drawing in terminal with unicode braille characters


##### webpack-dev-middleware
> An express-style development middleware for use with webpack bundles and allows for serving of the files emitted from webpack. This should be used for development only.

##### helmet  
> Helmet helps you secure your Express apps by setting various HTTP headers

##### chalk
> Terminal string styling

##### pug
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


### Vue 

#### tricks
```bash
# 拼接字符串 
:ref="`contact_key_${key}`"  

# 获取到组件内部传递出来的第一个参数
$event

```
#### vue-cli
```bash
# install
sudo npm install -g @vue/cli
vue --version

# crate 
vue create

```
#### vue-next
source code analysis

### Linux

```bash
# unzip tar.gz
tar -zxvf xx.tar.gz
# unzip tar.bz2
tar -jxvf xx.tar.bz2

# alsamixer
# alsamixer is a graphical mixer program for the Advanced Linux Sound Architecture (ALSA) that is used to configure sound settings and adjust the volume.
```


### ES6

#### [symbol](https://www.runoob.com/w3cnote/es6-symbol.html)
> ES6 引入了一种新的原始数据类型 Symbol ，表示独一无二的值，最大的用法是用来定义对象的唯一属性名。
ES6 数据类型除了 Number 、 String 、 Boolean 、 Object、 null 和 undefined ，还新增了 Symbol 

基本用法：

```es6
let sy = Symbol("KK");
console.log(sy);   // Symbol(KK)
typeof(sy);        // "symbol"
 
// 相同参数 Symbol() 返回的值不相等
let sy1 = Symbol("kk"); 
sy === sy1;       // false

```
特点：
1. 由于每一个 Symbol 的值都是不相等的，所以 Symbol 作为对象的属性名，可以保证属性不重名。
2. Symbol 作为对象属性名时不能用.运算符，要用方括号。因为.运算符后面是字符串，所以取到的是字符串 sy 属性，而不是 Symbol 值 sy 属性。
3. Symbol 值作为属性名时，该属性是公有属性不是私有属性，可以在类的外部访问。但是不会出现在 for...in 、 for...of 的循环中，也不会被 Object.keys() 、 Object.getOwnPropertyNames() 返回。如果要读取到一个对象的 Symbol 属性，可以通过 Object.getOwnPropertySymbols() 和 Reflect.ownKeys() 取到。
4. Symbol.for() 类似单例模式，首先会在全局搜索被登记的 Symbol 中是否有该字符串参数作为名称的 Symbol 值，如果有即返回该 Symbol 值，若没有则新建并返回一个以该字符串参数为名称的 Symbol 值，并登记在全局环境中供搜索
5. Symbol.keyFor() 返回一个已登记的 Symbol 类型值的 key ，用来检测该字符串参数作为名称的 Symbol 值是否已被登记。

#### Map

用法：
```ES6
// get / set
var myMap = new Map();
var keyString = "a string"; 
 
myMap.set(keyString, "和键'a string'关联的值");
myMap.get(keyString);    // "和键'a string'关联的值"

// key 
var keyString = string | object | function | NAN ; // NaN !== NaN 返回true

myMap.set(keyString, "和键'a string'关联的值");

// Iteration 
  // for ... of
var myMap = new Map();
myMap.set(0, "zero");
myMap.set(1, "one"); 
for (var [key, value] of myMap) {
  console.log(key + " = " + value); // 将会显示两个 log。 一个是 "0 = zero" 另一个是 "1 = one"
}
  // forEach
myMap.forEach(function(value, key) {
  console.log(key + " = " + value);
}, myMap)  //  arr.forEach(callback(currentValue [, index [, array]])[, thisArg]); 可选参数。当执行回调函数 callback 时，用作 this 的值。


// functions entries | keys | values ...
for (var key of myMap.keys()) {
  console.log(key);
}

# Map => Array
var kvArray = [["key1", "value1"], ["key2", "value2"]];
 
// Map 构造函数可以将一个 二维 键值对数组转换成一个 Map 对象
var myMap = new Map(kvArray);
 
// 使用 Array.from 函数可以将一个 Map 对象转换成一个二维键值对数组
var outArray = Array.from(myMap);
# Map clone
var myMap1 = new Map([["key1", "value1"], ["key2", "value2"]]);
var myMap2 = new Map(myMap1);
 
console.log(original === clone); 

# Map merge
var first = new Map([[1, 'one'], [2, 'two'], [3, 'three'],]);
var second = new Map([[1, 'uno'], [2, 'dos']]);
 
// 合并两个 Map 对象时，如果有重复的键值，则后面的会覆盖前面的，对应值即 uno，dos， three
var merged = new Map([...first, ...second]);

```

#### Set
> Set 对象允许你存储任何类型的唯一值，无论是原始值或者是对象引用。

```es6
# useage

let mySet = new Set();
 
mySet.add(1); // Set(1) {1}
mySet.add(5); // Set(2) {1, 5}
mySet.add(5); // Set(2) {1, 5} 这里体现了值的唯一性
mySet.add("some text"); 
// Set(3) {1, 5, "some text"} 这里体现了类型的多样性
var o = {a: 1, b: 2}; 
mySet.add(o);
mySet.add({a: 1, b: 2}); 
// Set(5) {1, 5, "some text", {…}, {…}} 
// 这里体现了对象之间引用不同不恒等，即使值相同，Set 也能存储

# Array to Set

var mySet = new Set(["value1", "value2", "value3"]);
// 用...操作符，将 Set 转 Array
var myArray = [...mySet];

# String to Set
var mySet = new Set('hello');  // Set(4) {"h", "e", "l", "o"}

# Array deduplication

var mySet = new Set([1, 2, 3, 4, 4]);
[...mySet]; // [1, 2, 3, 4]

# 并集

var a = new Set([1, 2, 3]);
var b = new Set([4, 3, 2]);
var union = new Set([...a, ...b]); // {1, 2, 3, 4}
# 交集

var a = new Set([1, 2, 3]);
var b = new Set([4, 3, 2]);
var intersect = new Set([...a].filter(x => b.has(x))); // {2, 3}
# 差集

var a = new Set([1, 2, 3]);
var b = new Set([4, 3, 2]);
var difference = new Set([...a].filter(x => !b.has(x))); // {1}

```

#### Proxy
#### Reflect



### TypeScript

#### ts with react
```sh
# install create-react-app
npm install -g create-react-app
# init project
create-react-app react-ts-app --template typescript

```

### MongoDB 
> [installation](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-red-hat/)
- Usage
  - service mongod status | start | stop


### Web Hacks



### Docker

- [install](https://docs.docker.com/install/linux/docker-ce/centos/) 

- dockerfile
```sh
# remove docker images

sudo docker images rm image_id

```

- docker compose
  - install 
```sh

sudo curl -L "https://github.com/docker/compose/releases/download/1.25.0/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

```

- docker network

```sh
# check
sudo docker network ls

# create
sudo docker network create paultest

```


### React Native

- [ ] wechat like post page
- [ ] ins like view page
- [ ] notifications
- [ ] user

#### useEffect, useRef ===> componentDidMount
> [react-hooks-and-component-lifecycle-equivalent](https://stackoverflow.com/questions/53254017/react-hooks-and-component-lifecycle-equivalent)



#### diff android and IOS

```js

// SafeAreaView for android
import { StyleSheet, Platform, StatusBar } from "react-native";

StyleSheet.create({
  SafeAreaView: {
    paddingTop: Platform.OS === "android" ? StatusBar.currentHeight : 0
  }
})



```





