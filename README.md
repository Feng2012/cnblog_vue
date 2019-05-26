# vue做的博客园webapp
详情可以看这边博客：[我用Vue写了个博客园WebApp]( https://www.cnblogs.com/xuhuale/p/10924576.html)

#### 如何运行：
##### Project setup
```
npm install
```
##### Compiles and hot-reloads for development
```
npm run serve
```
##### Compiles and minifies for production
```
npm run build
```
##### Run your tests
```
npm run test
```
##### Lints and fixes files
```
npm run lint
```

#### 如何配置
1.配置CLIENT_ID，CLIENT_SECRET
    配置CLIENT_ID，CLIENT_SECRET，首先你要有，可以去[博客园开发者](https://api.cnblogs.com/)申请。接着在`src/config/conf.js`中配置，如下：
    
``` javascript
export const CLIENT_ID = "XXXX";
export const CLIENT_SECRET ="XXXX";
```
    
2.配置环境

配置环境，主要是针对登录这个点，因为获取授权码的回调地址是博客园这边，但我们联系管理，帮我们改掉，所以这边的回调地址是根据你的实际情况的填写的，接着的登录环境也需要配置，若是你没办法改掉上诉所说的回调地址，意味着我们没有办法拿到授权码，所以登录环境设置为开发，可以引导用户去自己拿到授权码，自己登录，或是你像我改好了回调地址的话，那么就会自动登录。文件路径还是上个点的路径。

``` javascript
export const DEVELOPMENT = "development";
export const PRODUCTION = "production"
export const LOGIN_ENV = PRODUCTION; //development|production
export const LOGIN_REDIRECT_URI = "http://域名/auth/callback";//https://oauth.cnblogs.com/auth/callback

```
![回调地址没有改变的情况，引导式](https://i.loli.net/2019/05/26/5ceab3973a59b83642.jpg)

