# KMREOnArch
Porting Ubuntu kylin KMRE to archlinux.
# 使用方法
注意后面四行没有 `sudo`
```
sudo systemctl enable --now kylin-kmre-daemon.service
systemctl enable --user --now kylin-kmre-appstream.service
systemctl enable --user --now kylin-kmre-audio.service
systemctl enable --user --now kylin-kmre-filewatcher.service
systemctl enable --user --now kylin-kmre-manager.service
```

# 已知问题
`kmre-modules-dkms` 无法成功构建， 解决方案参考 [ArchWiki Anbox](https://wiki.archlinux.org/title/Anbox#Prerequisite).
目前整个容器还无法使用， 运行 `kmre-apk-installer` 提示 麒麟移动运行环境未安装。
`/usr/share/kylin-user-guide/data/guide/kmre/zh_CN` 下有说明文档，但是并未提及如何初始化。
# Todo
将包里的某些文件重命名，去掉 `kylin`, 如 `kylin-kmre-daemon.service` 改为
`kmre-daemon.service`。