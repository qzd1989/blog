# macos

## installation

- `brew install llvm@19 opencv`

## setting

```
# vim `~/.zshrc`
#llvm,因为指定了llvm@19的路径，将以下设置添加到~/.zshrc中
export PATH="/opt/homebrew/opt/llvm@19/bin:$PATH"
export LDFLAGS="-L/opt/homebrew/opt/llvm@19/lib"
export CPPFLAGS="-I/opt/homebrew/opt/llvm@19/include"
export LLVM_CONFIG="/opt/homebrew/Cellar/llvm@19/19.1.7/bin/llvm-config"
```

# windows

## installation

- `windowsdesktop-runtime-8.0.17-win-x64.exe`
- `rustup-init.exe`
- `node-v23.11.0-x64.msi`
- extract `opencv-4.11.0-windows.exe` to `C:\tools`
- move `clang+llvm-19.1.7-x86_64-pc-windows-msvc` to `C:\Program Files`, then rename to `LLVM`
- `Git-2.49.0-64-bit.exe`
- `python-3.13.3-amd64.exe`

## setting

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
setx PATH "%PATH%;C:\tools\opencv\build\x64\vc16\bin;C:\Program Files\LLVM\bin"

echo 配置完成。
pause
```
