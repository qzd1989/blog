# windows
## embed
* `https://www.python.org/downloads/windows/` 选择并下载embed版并解压么`C:\python-embed`
* 创建目录`C:\python-embed\lib\site-packages` 用于存放pip库
* `https://pypi.org/project/pip/25.0.1/#files` 下载 `pip-25.0.1-py3-none-any.whl`, 在macos上解压它 `midir pip_extracted && cd pip_extracted && python3 -m zipfile -e ../pip-25.0.1-py3-none-any.whl .`, 出来两个文件夹 `pip-25.0.1.dist-info`和`pip`
* 将`pip-25.0.1.dist-info`和`pip`直接复制到`windows`上的`C:\python-embed\lib\site-packages`,pip即可使用