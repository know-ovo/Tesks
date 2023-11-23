# Github的fork功能，在github上fork他人代码修改并创建Pull requests，Github跨团队合作开发



一、概述
        此功能的作用是您可以在Github一对开源项目添加您优化代码。 

       Fork允许你创建一个独立的项目副本，Pull Request则允许你将你的修改推送到原始项目中。这种方式促进了开源协作和贡献，使得项目能够从广泛的社区参与中受益。

二、fork 代码到您的Github仓库
        在github上搜索您要修改的项目代码，并fork到您的仓库中。这样Github会创建该项目的一个完全独立的副本，该副本存储在你自己的GitHub账号下。这个分叉副本可以独立进行修改和更改，而不会影响原始项目。



        执行完成后您可以在您的仓库中找到这个项目。



 三、修改代码
        修改代码您可以先使用git clone将代码克隆到你的电脑上，对代码进行修改后再提交到您的Github仓库中。如果您 对git clone、git add、git commit相关指令您还不熟悉，请参考在命令行中使用Git或在IDEA中使用Git。

四、创建Pull requests
        你对分叉项目进行了一些修改后，你可以提交一个"Pull Request"，也就是提出一个请求，要求原始项目的维护者（或者说项目的所有者）合并你的更改到原始项目中。这个请求包含了你所做的修改的详细描述和解释。维护者可以查看你的更改，讨论其中的细节，最终决定是否接受你的更改并将其合并到原始项目中

        这时您需切换到Pull requests选项卡，点击 New pull requests并填写相关提交日志信息后点击Create pull requests来创建。



五、拉取Pull requests 合并【注意此处角色切换】
        如果是您是原开发者，此项目被别人fork然后修改了内容，则您可以打开您项目的Pull requests选项卡。打开之后会看到他人修改的代码详细信息，您可以根据情况选择合并（Merge pull requests）



原文链接：https://blog.csdn.net/qifu123/article/details/132478701