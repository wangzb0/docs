#### PicGo

#### 1. 安装node.js

[node.js](https://nodejs.org/zh-cn/download/)

#### 2. 配置环境变量（可跳过）

在以上的步骤已经完成了Node.js的安装，即使不进行此步骤的环境变量配置也不影响Node.js的使用。但是如果不进行环境变量配置，那么在我们使用命令安装Node.js全局模块，例如npm install -g express时，会默认安装到C盘的路径C:\Users\Administrator\AppData\Roaming\npm中，所以在这边配置全局安装模块以及缓存目录的环境变量。

---

1. 首先在node.js的安装目录新建两个文件夹node_global和node_cache

   ![](https://img-blog.csdnimg.cn/20200114230859571.png)

2. 创建完两个文件夹后，在cmd窗口中输入以下命令（两个路径即是两个文件夹的路径）：设置全局安装模块路径以及缓存目录。

   ```shell
   npm config set prefix "D:\install\nodejs\node_global"
   npm config set cache "D:\install\nodejs\node_cache"
   ```

   若是忘记了自己设置的全局安装模块路径和缓存路径，可以在cmd窗口中输入以下命令获取

   ```shell
   nmp get prefix #得到全局安装模块路径
   nmp get cache  #得到缓存路径
   ```

   提及：在cmd窗口中，输入的路径若是含有空格，使用英文半角双引号包裹。

3. 接下来设置电脑环境变量，右键“我的电脑”=》属性=》高级系统设置=》环境变量 进入以下环境变量对话框

   ![](https://img-blog.csdnimg.cn/20200114230821885.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3hpYW90aWFuMjUxNg==,size_16,color_FFFFFF,t_70)

4. 在【系统变量】新建环境变量 NODE_PATH，值为

   D:\install\nodejs\node_global\node_modules，其中D:\install\nodejs\node_global是上述创建的全局模块安装路径文件夹

   ![](https://img-blog.csdnimg.cn/20200114230023367.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3hpYW90aWFuMjUxNg==,size_16,color_FFFFFF,t_70)

5. 修改【用户变量】中的path变量，将C:\Users\Administrator\AppData\Roaming\npm修改为D:\install\nodejs\node_global

   ![](https://img-blog.csdnimg.cn/20200114225702754.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3hpYW90aWFuMjUxNg==,size_16,color_FFFFFF,t_70)

6. 点击确定后，配置完成。（***\*注意\****：环境变量配置完成后，最好重启电脑或者重启资源管理器）

7. 测试是否配置成功，在cmd窗口中输入以下指定全局安装express模块

   ```shell
   npm install -g express
   ```

![](https://img-blog.csdnimg.cn/20200114224429174.png)

注意：-g表示全局安装，安装在配置的环境D:\install\nodejs\node_global\node_modules中。若是不设置-g，则安装在当前目录下。例如

```powershell
D:\space>npm install express
```

以上则安装在D:\space中。

#### 3. 国内镜像网站配置

我们通过npm命令下载node模块的时候因为访问的是国外网站，所以可能会出现下载的很缓慢或者干脆是直接下载失败，在这种情况下，我们可以通过配置国内镜像来解决，一般配置的是[淘宝npm镜像](http://npm.taobao.org/)

1. 通过以下命令配置淘宝镜像

   ```shell
   npm install -g cnpm --registry=https://registry.npm.taobao.org
   ```

2. 以后下载模块的时候，将npm替换成cnpm即可从淘宝镜像中下载模块，例如：

   ```shell
   cnpm install
   ```

#### 4. PicGo-GItHub设置

![github](https://gitee.com/wangzb0/images/blob/master/images/20200402111420.png)

#### 5. GitHub-Token生成

![token](https://gitee.com/wangzb0/images/blob/master/images/20200402111909.png)

#### 6. PicGo下载

[PicGo](https://molunerfinn.com/PicGo/)