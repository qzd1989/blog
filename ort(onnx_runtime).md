# windows

- 遇到有关 paddle-ocr 的报错,先执行下面的步骤,安装好 ort 环境:
  1. 下载: `https://parcel.pyke.io/v2/delivery/ortrs/packages/msort-binary/1.20.0/ortrs_static-v1.20.0-aarch64-pc-windows-msvc.tgz`
  2. 解压到: `C:\onnxruntime`
  3. 添加环境变量: `ORT_LIB_LOCATION`:`C:\onnxruntime\lib`
