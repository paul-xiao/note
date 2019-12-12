# Daily Notes


## Table of content
- [Nginx](#nginx)
- [Tools](#tools)
  - [Vscode](#vscode)
- [Git](#git-usages)
- [Node](#node)
  - [Node Install](#node-install)
  - [Node Packages](#node-packages)
- [Vue](#vue)
  - [Vue Cli](#vue-cli)
- [Linux](#linux)
- [ES6](#es6)
- [MongoDB](#mongodb)
- [Web Hacks](#web-hacks)
- [Docker](#docker)

--------------

### Tools

#### Vscode
- Extensions
> JSHint, a tool that helps to detect errors and potential
  problems in your JavaScript code.

```bash
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

### Nginx

- sudo systemctl start nginx
- root directory :usr/share/nginx/html
- sudo ./nginx -t


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

#Reset the upstream branch for the new-name local branch.
#Switch to the branch and then:

git push origin -u new-name

# update git version

yum install http://opensource.wandisco.com/centos/7/git/x86_64/wandisco-git-release-7-2.noarch.rpm

yum install git 

git --verison

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
export PATH=$PATH:/home/paul.xiao/npm_global/bin/  

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

### Linux

```bash
# unzip tar.gz
tar -zxvf xx.tar.gz
# unzip tar.bz2
tar -jxvf xx.tar.bz2

# alsamixer
# alsamixer is a graphical mixer program for the Advanced Linux Sound Architecture (ALSA) that is used to configure sound settings and adjust the volume.
```


### [ES6](https://www.w3schools.com/js/js_es6.asp)

```js

// New Global Methods
  - isFinite()
  - isNaN()

// symbol

// proxy

// set/weekSet ...


``` 


### MongoDB 
> [installation](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-red-hat/)
- Usage
  - service mongod status | start | stop


### Web Hacks
> image 



### Docker

> install 

```