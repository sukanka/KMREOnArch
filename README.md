# KMREOnArch
Porting Ubuntu kylin KMRE to archlinux.
# Usage
note the last 4 commands is for user, so not requiring `sudo`
```
sudo systemctl enable --now kylin-kmre-daemon.service
systemctl enable --user --now kylin-kmre-appstream.service
systemctl enable --user --now kylin-kmre-audio.service
systemctl enable --user --now kylin-kmre-filewatcher.service
systemctl enable --user --now kylin-kmre-manager.service
```

## Clarification
Some packages are not included.

- `kmre-peony-vfs`: [Its repo](https://gitee.com/openkylin/peony-vfs-kylin-kmre) has nothing, and named `peony-vfs-kylin-kmre`
-  [kmre-modules-dkms](https://gitee.com/openkylin/kylin-kmre-modules-dkms):  no longer needed for `linux` and `linux-zen`, as stated by [archwiki](https://wiki.archlinux.org/title/Waydroid#Kernel_Modules)
- `libkmre`: deleted, it's an Android application.

## Todo list
### general
- rename all package name to `kylin-kmre-xxx`
- check information for PKGBUILD like license and pkgver.
- all modification in `prepare()` should be reported to upstream.

### specific
- `kmre-image-data`: lacks `kmre-container-image.tar` which is not included in [the repo](https://gitee.com/openkylin/kylin-kmre-image-data), also, there is `kmre-image-data-x64` but their `kmre.conf` is the same, only `kmre-container-image.tar` differs, so there is no needed to package them separately.

- `kmre-window` : cannot be built with `ffmpeg-7.0`, a similar issue is at [OpenBoard](https://github.com/OpenBoard-org/OpenBoard/issues/1002), we should add a patch for it.
