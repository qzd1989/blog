# windows

- 去`https://github.com/llvm/llvm-project/releases`找一个符合当前架构的如: `clang+llvm-20.1.1-aarch64-pc-windows-msvc.tar.xz`,这种包是解压即用,且包含`clang.exe`和`llvm-config.exe`等,这个版本是属于包含了开发者工具的版本,将其解压后放在目录`C:\Program Files\LLVM`,然后将`C:\Program Files\LLVM\bin`写入`Path`即可正常使用.
- `LLVM-20.1.1-win64.exe`是用户版,不含开发者工具.

## opencv 4.11.0 can't work with llvm 20.1.3, can to work with llvm 18.1.8

1. macos `brew install llvm@18 opencv`
2. check `~/.zshrc`

```
export PATH="/opt/homebrew/opt/llvm@18/bin:$PATH"
export LDFLAGS="-L/opt/homebrew/opt/llvm@18/lib"
export CPPFLAGS="-I/opt/homebrew/opt/llvm@18/include"
```
