---
layout:     post
title:      如何使用多个GitHub账户
subtitle:   多账号 GitHub SSH
date:       2018-06-22
author:     Pancratius
header-img: img/post-bg-cook.jpg
catalog: true
tags:
    - cocoapods
    - 更新
---


1.先切换gem源
```
gem sources --remove https://rubygems.org/
gem source -a https://gems.ruby-china.org
```

2.查看是否切换成功
```
gem source -l
```

3.查看是否成功
```
*** CURRENT SOURCES ***
https://gems.ruby-china.org
```

4.切换成功后，接下来就可以开始升级了cocoapods了
```
sudo gem install cocoapods
```

5.查看是否升级成功
```
pod --version
```

6.升级成功后的版本号
```
1.5.3
```

7.设置pod仓库
```
pod setup
```

8.setup成功
```
Setup completed
```
