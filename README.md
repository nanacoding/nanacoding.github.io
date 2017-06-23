# nanacoding.github.io
博客的产生得益于同事的分享和以下这份教程
https://cczeng.github.io/2017/05/03/%E6%88%91%E6%98%AF%E5%A6%82%E4%BD%95%E5%88%A9%E7%94%A8Github-Pages%E6%90%AD%E5%BB%BA%E8%B5%B7%E6%88%91%E7%9A%84%E5%8D%9A%E5%AE%A2%E2%80%94%E2%80%94%E7%BB%86%E6%95%B0%E4%B8%80%E8%B7%AF%E7%9A%84%E5%9D%91/


#mark下操作步骤（windows）：

1. 环境准备：  
  包括git、node.js、npm设置淘宝镜像
  
2. 初始化博客  
  ```
  #!bash
  $ cnpm install hexo-cli -g  
  $ hexo init blog  
  $ cd blog  
  $ cnpm install  
  $ hexo g # 或者hexo generate  
  $ hexo s # 或者hexo server，可以在http://localhost:4000/ 查看  
  ```
  
3. git设置publicKey  
  git bash中生成publicKey   
  `$ ssh-keygen -t rsa -b 4096 -C "your_email@example.com"`  
  找到公钥文件id_rsa.pub，默认目录为C:/Users/[username]/.ssh，用文本编辑器打开并复制  
  然后打开github网站，可以将公钥添加为项目公钥也可以添加为账户公钥  
  
    添加为项目公钥步骤：进入项目点击Settings->Deploy keys->Add Deploy key.  
    具体可以参考:[Generating a new SSH key and adding it to the ssh-agent](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/)

  
4. 提交[部署](https://hexo.io/zh-cn/docs/deployment.html)  
  安装hexo-deployer-git  
  `$ npm install hexo-deployer-git --save`  
  修改配置（冒号后面一定要跟空格）  
    deploy:  
    type: git  
    repo: git@github.com:nanacoding/nanacoding.github.io.git  
    branch: master  
  部署到github，在git bash中执行 hexo d（publicKey只有在git bash中有效）  
