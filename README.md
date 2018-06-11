记录一下项目心得

### 关于前端  

>- 底部菜单active状态问题，刷新页面后要保证active状态是对的  

>- 分类页面数据不会经常更新，用localStorage做缓存  

>- localStorage本身没有过期时间，所以存的时候自己存一个expire字段，取的时候判断是否过期  

>- 移动端开始搜索后，要让搜索框失去焦点，这样手机键盘会收回去  

>- 加载动画必须要，不然体验太差了  

>- 请求的时候要判断是否正在进行别的请求，如果是就取消本次请求  

>- 进入某些页面要 window.scroll(0,0) 滚动到顶部  

>- vue页面数据交互可以用vuex，也可以在路由配置的时候加上参数，也可以跟以前一样用?a=1&b=1这种方式  

>- 这个项目中，由于翻页的时候路由不会变，只是参数在变，所以从详情页返回列表页的时候，总是会返回第一页，要保存一下翻页的进度  
>- 由于保存了翻页进度，换一个分类进入列表页，会显示已保存的翻页进度，所以进入分类页要删除翻页进度    

>- 书架功能也是用localStorage来存的，由于小说可能重名，所以键名用书的url  

>- 书架有继续上次阅读的功能，所以每次离开章节内容页的时候，要判断是否在书架，如果在则把该章节存到localStorage  

>- localStorage缓存大小怎么算，其实缓存大小就是所有键值加起来的字节数，单位Byte  

>- axios请求失败的处理，要在配置文件里配置，可以重新发起请求，也可以报错  

>- 本来想用vue-router的路由缓存的，但是发现不该缓存的都缓存了，就算了，没有深入研究  

>- 夜间模式、字体大小这些都是存localStorage，触发条件就是点击屏幕中间，所以要做点击位置的判断  

>- 移动端还有一些滑动操作，可以去github找别人写的插件  

>- 由于浏览器访问http经常被植入js广告，所以用https  

### 关于后端  

>- lumen注意路由书写的顺序，避免上一条路由会拦截下面一条路由的情况  

>- queryList爬取网页的时候都removeHead,强制设置UTF-8  

>- ajax跨域问题，laravel有个lavavel-cors包可以直接用，lumen没有，网上找或者自己写一个全局路由中间件  

>- lumen的storage文件夹的权限问题，一定要可读可写  

>- lumen自定义配置文件后，要在bootstrap/app.php里加上 $app->configure('文件名');  

### 关于打包成app  

>- HBuilder打包的时候要注意资源的路径，不能用绝对路径，要用相对的  

>- 如果打算上架应用商店，打包的时候记得把包名记下来  

### 关于上架应用商店  

>- 现在各大应用商店审核比较严格，上架app需要著作权证书、不侵权、广告要符合各个商店的要求等等，我这个提交到酷安都一周了都没审核通过，另外，app说明、图片等等都要不同的要求，照着做就行  

>- 上架的时候一般都要你加固app，用腾讯出的乐加固就可以了。加固的时候需要KeyStore文件，HBuilder公有证书信息如下：
`
签名证书KeyStore文件 下载地址: http://download.dcloud.net.cn/HBuilder.keystore
证书别名：hbuilder
证书密码：123456
keystore密码：123456
`  

