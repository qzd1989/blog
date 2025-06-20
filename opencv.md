# windows

1. 去`https://github.com/opencv/opencv/releases` 找到最新版并下载 `opencv-4.11.0-windows.exe` 类似名称
2. 在系统上运行,并 extract 到`C:\tools`
3. 安装完后,进行环境变量的配置:
   - `OPENCV_DIR`:`C:\tools\opencv\build`
   - `OPENCV_INCLUDE_PATHS`: `C:\tools\opencv\build\include`
   - `OPENCV_LINK_LIBS`: `C:\tools\opencv\build\x64\vc16\lib\opencv_world4110.lib`
   - `OPENCV_LINK_PATHS`: `C:\tools\opencv\build\x64\vc16\lib`
   - 将`C:\tools\opencv\build\x64\vc16\bin`添加到`Path`中

## 批处理文件,保存,右键,管理员执行.

```bat
@echo off

REM 检查是否以管理员权限运行
openfiles >nul 2>nul
if %errorlevel% neq 0 (
    echo 请以管理员权限运行此脚本!
    pause
    exit /b
)

REM OpenCV setting
setx OPENCV_DIR "C:\tools\opencv\build"
setx OPENCV_INCLUDE_PATHS "C:\tools\opencv\build\include"
setx OPENCV_LINK_LIBS "C:\tools\opencv\build\x64\vc16\lib\opencv_world4110.lib"
setx OPENCV_LINK_PATHS "C:\tools\opencv\build\x64\vc16\lib"

REM Path adding
setx PATH "%PATH%;C:\tools\opencv\build\x64\vc16\bin"

echo OpenCV 环境变量已配置完成。
pause
```

## opencv 4.11.0 can't work with llvm 20.1.3, can to work with llvm 19.1.7
