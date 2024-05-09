# 介绍

用于数值计算课程的公式纸，由于不会latex，于是用html+css实现分栏，读取markdown合并，再用浏览器的打印功能导出A3即可

# 辅助工具

图片转latex

https://simpletex.cn/

# pdf资源下载

用于识别出latex公式

https://wp.007irs.com/s/7kLhn

# 本地开发指南

`fork`本项目，`git clone`到本地

`VSCODE`安装`Live Server`插件

![](./live_server.png)

在`text.html`右键选择 Open with live server 即可预览

![](./open.png)

不同数字的文件夹用于不同单元的内容，使用`markdown`+`latex`语法

建议使用`###`作为标题头

使用`latex`需要使用 $行内公式$ 或者 $$单行公式$$，可以借助`simpletex`识别图片导出为`markdown`的`$`格式

开发后可以在网页预览或者在本地markdown编辑器预览

完成后提交 pr 即可合并 https://github.com/xy3xy3/NumericalMethodsFormulaPaper/pulls 