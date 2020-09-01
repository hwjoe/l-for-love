# webpack怎么安装 #

webpack怎么安装

1、安装node.js;

2、创建配置文件【package.json】;

3、安装webpack：【npm install webpack --save-dev】；


webpack安装

1.在电脑上安装node.js，

2.node.js自带npm，所以node.js安装完成后，不需要再安装npm；输入命令【npm -v】，可查看当前npm的版本，

3.在项目文件夹中创建【package.json】配置文件，

4.安装webpack，通过cmd进入项目根目录文件夹，输入【npm install webpack --save-dev】,然后按回车键，

5.需要等待一会，最后显示出webpack的版本信息，然后打开【package.json】配置文件，可以看到这里也有了webpack的版本信息，

6.然后打开项目根目录文件夹，在该文件夹下生成了一个【node_modules】文件，

 
安装webpack-cli

1. 在cmd中进入项目根目录，输入命令【webpack -v】，查看当前webpack的版本信息，得到提示：不是内部或外部命令……

注意:webpack 4x以上，webpack将命令相关的内容都放到了webpack-cli，所以还需要安装webpack-cli；

2. 输入命令【npm install --save-dev  webpack-cli】，然后按回车键，

3. 然后在输入命令【webpack -v】，按回车键，得到提示：不是内部或外部命令……，说明webpack还是没有安装成功，

4. 输入命令【npm install --global webpack】，按回车键；然后在输入命令【webpack -v】，按回车键，依然没有出现webpack的版本信息，

5. 就继续输入命令【npm install --global webpack-cli】，按回车键；然后在输入命令【webpack -v】，按回车键，出现webpack的版本，就说明安装成功，

链接：https://jingyan.baidu.com/article/a3a3f811230ee58da3eb8a6e.html
