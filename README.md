# Star Rail Grub Themes
星穹铁道GURB主题  
对 https://www.gnome-look.org/p/2076542 的图像超分辨率再剪切

# Demo
![img](./img/img_1.jpg)

# 使用
1. 克隆本仓库
```bash
git clone https://github.com/xmexg/Star_Rail_Grub_Themes.git
```

2. 把本仓库内容复制到 `/boot/grub/themes` 目录下
```bash
sudo cp -r Star_Rail_Grub_Themes/* /boot/grub/themes/
```

3. 修改主题文件, 把 `GRUB_THEME` 改成要使用的主题的路径   
kali: `/etc/default/grub.d/kali-themes.cfg`
```bash
sudo vim /etc/default/grub.d/kali-themes.cfg
```
```shell
GRUB_THEME="/boot/grub/themes/Firefly_cn/theme.txt"
```

4. 更新 GRUB 配置
```bash
sudo update-grub
```


# 可选
  + 添加 `重启/关机` 选项  
  编辑`/etc/grub.d/40_custom`文件，使其变成如下样式
  ``` shell
#!/bin/sh
exec tail -n +3 $0
# This file provides an easy way to add custom menu entries.  Simply type the
# menu entries you want to add after this comment.  Be careful not to change
# the 'exec tail' line above.

menuentry "关机" --class halt {
    echo "正在关机..."
    halt
}

menuentry "重启" --class reboot {
    echo "正在重启..."
    reboot
}

  ```