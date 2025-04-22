# windows

1. 去`https://github.com/opencv/opencv/releases` 找到最新版并下载 `opencv-4.11.0-windows.exe` 类似名称
2. 在系统上运行,并extract到`C:\tools`
3. 安装完后,进行环境变量的配置:
    * `OPENCV_DIR`:`C:\tools\opencv\build`
    * `OPENCV_INCLUDE_PATHS`: `C:\tools\opencv\build\include`
    * `OPENCV_LINK_LIBS`: `C:\tools\opencv\build\x64\vc16\lib\opencv_world4110.lib`
    * `OPENCV_LINK_PATHS`: `C:\tools\opencv\build\x64\vc16\lib`
    * 将`C:\tools\opencv\build\x64\vc16\bin`添加到`Path`中