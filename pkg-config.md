# windows

- 安装 msys2 `https://www.msys2.org/`,本地离线我下载的有
  `msys2-x86_64-20250221.exe`,运行安装后记得把打开的窗口锁定在任务栏,不然找不到在哪重新打开了我靠.
- 在窗口里执行`pacman -Syu`更新,完了之后再打开,再执行`pacman -S pkgconf mingw-w64-x86_64-pkg-config`,结束后再将`C:\msys64\mingw64\bin` 写入到`Path`
