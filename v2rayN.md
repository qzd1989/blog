# windows

- proxy 端口为`10809`,proxy 的地址为`http://127.0.0.1:10809`
- 设置 powershell 里的代理:

```
[Environment]::SetEnvironmentVariable("http_proxy", "http://127.0.0.1:10809", "User")
[Environment]::SetEnvironmentVariable("https_proxy", "http://127.0.0.1:10809", "User")
```
