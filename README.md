# KMREOnArch
Porting Ubuntu kylin KMRE to archlinux.
## Usage
note the last 4 commands is for user, so not requiring `sudo`
```
sudo systemctl enable --now kylin-kmre-daemon.service
systemctl enable --user --now kylin-kmre-appstream.service
systemctl enable --user --now kylin-kmre-audio.service
systemctl enable --user --now kylin-kmre-filewatcher.service
systemctl enable --user --now kylin-kmre-manager.service
```

## Todo list
### general
- all modification in `prepare()` should be reported to upstream.

### specific
- `kmre-image-data`: lacks `kmre-container-image.tar` which is not included in [the repo](https://gitee.com/openkylin/kylin-kmre-image-data), also, there is `kmre-image-data-x64` but their `kmre.conf` is the same, only `kmre-container-image.tar` differs, so there is no needed to package them separately.
