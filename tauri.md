# error: Permission dialog:default/xxx not found

```toml
#检查Cargo.toml里的写法是否正确
#错误示例:
[dependencies]
tauri = { version = "2", features = [] }
tauri-plugin-opener = "2.2.7"
serde = { version = "1", features = ["derive"] }
serde_json = "1"

[target.'cfg(target_os = "macos")'.dependencies]
objc2 = "0.6.1" #截屏时使kiwi窗口透明

[target.'cfg(target_os = "windows")'.dependencies]
windows = { version = "*", features = [
    "Win32_UI_WindowsAndMessaging",
] } #截屏时使kiwi窗口透明

tauri-plugin-dialog = "2"
tauri-plugin-fs = "2"
tauri-plugin-os = "2"
tauri-plugin-websocket = "2"
tauri-plugin-store = "2"
tauri-plugin-clipboard-manager = "2"
tauri-plugin-pinia = "3.4.0"
tauri-plugin-shell = "2"

#它会使tauri-plugin-*只在windows下生效
```
