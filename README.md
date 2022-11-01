# OpenVINO-Python-FreeYOLO

## Requirements
- We recommend you to use Anaconda to create a conda environment:
```Shell
conda create -n openvino_yolo python=3.6
```

- Then, activate the environment:
```Shell
conda activate openvino_yolo
```

- Requirements:
```Shell
pip install -r requirements.txt 
```

## Download FreeYOLO ONNX file
Main results on COCO-val:

| Model          |  Scale  |    AP    |    AP50    |  ONNX  |  XML  |
|----------------|---------|----------|------------|--------|-------|
| FreeYOLO-Nano  |  416    |      |        |  |  |
| FreeYOLO-Tiny  |  416    |      |        |  |  |
| FreeYOLO-Large |  640    |   47.1   |   67.4     | [github](https://github.com/yjh0410/FreeYOLO/releases/download/weight/yolo_free_large_opset_11.onnx) |  [github](https://github.com/yjh0410/FreeYOLO/releases/download/weight/yolo_free_large.xml) |
| FreeYOLO-Huge  |  640    |     |        |  |  |


## ONNXRuntime Demo
For example:

```shell
python3 openvino_inference.py --weight weights/xml/yolo_free_large.xml -i test_image.jpg -s 0.3 -size 640
```
or
```shell
python3 openvino_inference.py --weight weights/onnx/yolo_free_large_opset_11.onnx -i test_image.jpg -s 0.3 -size 640
```

Notes:
* --weight: your converted onnx model or xml model
* -i: input_image
* -s: score threshold for visualization.
* --img_size: should be consistent with the shape you used for onnx convertion.
