# mt-app ———— 仿美团官网

> vue+nuxt+koa+mongodb+redis

## Build 

+ 环境准备：

> + 安装node 
> + 安装mongodb
> + 安装studio 3T
> + 安装redis

+ 连接数据库

> + 启动mongodb
> + web端配置数据库
``` javascript
// server/dbs/dbConfig.js
export default {
    //连接本地/远程数据库
    dbs: 'mongodb://127.0.0.1:27017/student',
    //配置redis
    redis: {
        get host() {
            return '127.0.0.1'
        },
        get port() {
            return 6379
        }
    }
}

//server/index.js

//引入
import dbConfig from './dbs/config'

//连接数据库
mongoose.connect(dbConfig.dbs, {
  useNewUrlParser: true
})

//server/dbs/models/xxx.js
//创建mongoose模型
import mongoose from 'mongoose'
const Schema = mongoose.Schema
const UserSchema = new Schema({
  username: {
    type: String,
    unique: true,
    require: true
  },
})
export default mongoose.model('User', UserSchema)
```
> + 启动redis

+ npm install
> * vuex
> * mongoose
> * axios
> * koa 

## start
``` bash
# install dependencies
$ npm install

# serve with hot reload at localhost:3000
$ npm run dev

# build for production and launch server
$ npm run build
$ npm run start

# generate static project
$ npm run generate
```

