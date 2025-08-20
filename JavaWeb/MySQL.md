# MySQL

### 一、下载

官网下载地址： https://downloads.mysql.com/archives/installer/

![[mysql_download.png]]

1. 通过 ==Product Version== 下拉框选择要下载的版本；
2. 通过 ==Operation System== 下拉框选择对应的操作系统；
3. 通过下面的 ==Windows (x86, 32-bit), MSI Installer== 后面的下载按钮下载即可，第一项为在线安装，本教程将采用第二项的安装包进行安装；

下载完成后我们将得到后缀为.msi的安装包文件：==mysql-installer-community-8.0.43.0.msi==。

### 二、安装

1. 双击运行 ==mysql-installer-community-8.0.43.0.msi== 安装

![[mysql_installer_setup_type.png]]

- Server only: 仅作为服务器安装
- Client only: 仅作为客户端安装
- Full: 完整安装
- Customer: 自定义安装

可以根据实际需求选择对应的安装方式，这里我们将选择自定义安装，点击 'Next'。

2. 依次展开 ==MySQL Servers==，单击选中 ==MySQL Server 8.0.43 - X64==（当前只有64位版本的服务器，其他版本的安装包中可能会有32位的。），点击中间的右箭头，同时下方的复选框（Enable the Select Features page to customize product features），最后点击 'Next'。
![[mysql_installer_select_products.png]]

3. 设置 MySQL 的安装路径和数据的存放路径，建议不要将数据直接存储在C盘，确保无误后点击 'Next'。

![[mysql_path_conflicts.png]]

4. 保持默认勾选，点击 'Next'

![[mysql_select_features_to_install.png]]

5. 点击 'Execute' ，执行完成后，点击 'Next'
6. 点击 'Next' 对 MySQL 进行配置
7. 保持默认配置即可，如果端口号已经被其他程序占用，则可以将默认端口 3306 修改成其他数值。点击 'Next'

![[mysql_configure.png]]

8. 点击 'Next'
9. 设置 MySQL 密码，点击 'Next'

![[mysql_password.png]]

10. 点击 'Next'
11. 点击 'Next'
12. 点击 'Execute'
![[mysql_configuration_apply.png]]

13. 当所有步骤执行完毕后，出现下图所示界面，则表示安装成功，点击 'Finish'
![[mysql_done.png]]


### 三、验证

1. Win + r 输入cmd
2. 在命令提示符中输入 `netstat -ano | findstr 3306`，回车，出现如下图所示，则表示 MySQL 安装成功，同时 MySQL 服务启动成功（可选）。
![[mysql_verify.png]]

3. 在开始菜单中找到 MySQL 目录，点击 MySQL Command Line Client。
![[mysql_client.png]]
4. 进入MySQL命令行客户端，输入配置的密码。
![[mysql_client_enter.png]]







