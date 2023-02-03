# webpack的chunk、bundle、module是什么
## module
module 是js和被js组织起来的任意文件

## chunk
chunk是被js组织起来的文件依赖结构

## bundle
bundle是我们最终输出的js文件，包括main.js,vendor.js,动态引入的js。
如：`()=> import( /* webpackChunkName: "print" */ './print')`