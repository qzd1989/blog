# macos

> Python 3.9.6
* 模型转换什么的没必要在windows上运行,杂方便杂来.
* 先upgrade`pip install --upgrade pip setuptools`
* 安装必要包`pip install setuptools numpy wheel common dual tight data prox onnx paddle2onnx paddlepaddle`
* 需要注意的是 `paddlepaddle`这个包,而不是`paddle`这个包,可能好名字被优先占用了
* 去官网下载模型`https://paddlepaddle.github.io/PaddleOCR/main/ppocr/model_list.html`,注意下最新的和观察他们的大小(推理模型是直接使用的,训练模型是供二次训练和调优的,使用的话直接下载训练模型).
* 将ch_PP-OCRv4_rec_infer.tar和ch_PP-OCRv4_det_infer.tar解压到目录下,保持文件夹结构如下:
```
paddle/
    ch_PP-OCRv4_rec_infer/
        inference.pdiparams
        inference.pdiparams.info
        inference.pdmodel
    ch_PP-OCRv4_det_infer/
        inference.pdiparams
        inference.pdiparams.info
        inference.pdmodel
```
* 运行 `paddle2onnx -m ./ch_PP-OCRv4_det_infer -mf inference.pdmodel -pf inference.pdiparams -s detection_inference.onnx`
* 运行 `paddle2onnx -m ./ch_PP-OCRv4_rec_infer -mf inference.pdmodel -pf inference.pdiparams -s recognize_inference.onnx`
* 此时`paddle`文件夹下会有两个文件`recognize_inference.onnx`和`detection_inference.onnx`,观察他们的大小,然后运行`python3 check.py`检查模型.
```python
# check.py的代码如下
import onnx
model = onnx.load("detection_inference.onnx")
onnx.checker.check_model(model)
model = onnx.load("recognize_inference.onnx")
onnx.checker.check_model(model)
print("model pass if there has no any outputs before")
```