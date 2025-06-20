# windows

## installation

- 去`https://github.com/llvm/llvm-project/releases`找一个符合当前架构的如: `clang+llvm-20.1.1-aarch64-pc-windows-msvc.tar.xz`,这种包是解压即用,且包含`clang.exe`和`llvm-config.exe`等,这个版本是属于包含了开发者工具的版本,将其解压后放在目录`C:\Program Files\LLVM`,然后将`C:\Program Files\LLVM\bin`写入`Path`即可正常使用.
- `LLVM-20.1.1-win64.exe`是用户版,不含开发者工具.

```bat
@echo off

REM 检查是否以管理员权限运行
openfiles >nul 2>nul
if %errorlevel% neq 0 (
    echo 请以管理员权限运行此脚本!
    pause
    exit /b
)

REM Path adding
setx PATH "%PATH%;C:\Program Files\LLVM\bin"

echo 配置完成。
pause
```

## opencv 4.11.0 can't work with llvm 20.1.3, can work with llvm and 19.1.7

1. macos `brew install llvm@19 opencv`
2. check `~/.zshrc`

```
#llvm,因为指定了llvm@19的路径，所以需要在这里设置
export PATH="/opt/homebrew/opt/llvm@19/bin:$PATH"
export LDFLAGS="-L/opt/homebrew/opt/llvm@19/lib"
export CPPFLAGS="-I/opt/homebrew/opt/llvm@19/include"
export LLVM_CONFIG="/opt/homebrew/Cellar/llvm@19/19.1.7/bin/llvm-config"
```
