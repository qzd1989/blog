# windows

- proxy 端口为`10809`,proxy 的地址为`http://127.0.0.1:10809`

- 查看 powershell 里的代理:

```
Get-Item Env:HTTP_PROXY
Get-Item Env:HTTPS_PROXY
```

- 设置 powershell 里的代理:

```
[Environment]::SetEnvironmentVariable("http_proxy", "http://127.0.0.1:10809", "User")
[Environment]::SetEnvironmentVariable("https_proxy", "http://127.0.0.1:10809", "User")
```

- 删除 powershell 里的代理:

```
[Environment]::SetEnvironmentVariable("http_proxy", $null, "User")
[Environment]::SetEnvironmentVariable("https_proxy", $null, "User")
```
