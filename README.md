# quantization-from-scratch
This repository offers a PyTorch reimplementation of the quantization approach outlined in the white paper "Integer Quantization for Deep Learning Inference: Principles and Empirical Evaluation." Please consult the paper for detailed information and empirical data, which you can access at [arXiv:2004.09602](https://arxiv.org/abs/2004.09602). The codebase includes the reimplementation of 8-bit inference methods, drawing on the strategies discussed in "8-bit Inference with TensorRT," presented at GTC 2017, available [here](https://on-demand.gputechconf.com/gtc/2017/presentation/s7310-8-bit-inference-with-tensorrt.pdf).

![Example Image](/images/quantization_flow.drawio.png "Quantization Flow")

Goal: This repository is dedicated to those who wish to comprehend the process of quantization within the PyTorch framework. It offers a straightforward and accessible implementation, as well as practical demonstrations of model size reduction with ONNX inference. 

#Default Quantization Setting
Activation: int8
Weight: int8
reduced range(-127 ~ 127)
symmatric quantization (zero point = 0)

## Requirements
- PyTorch: 2.2.1
- CUDA: 12.1
- timm: 0.9.12
- ONNX: 1.16.0
- ONNX Runtime: 1.17.1

  ##Run
____________________________________________________________________________________________

To PTQ + QAT
<pre>
python run.py
</pre>

| Model Name           | Accuracy (%) | Size (MB) | Latency (ms) |
|----------------------|--------------|-----------|--------------|
| pytorch_resnet18_fp  | 73.66        | 44.98     | 16.3784      |
| onnx_resnet18_quant  | 73.52        | 11.35     | 10.2182      |





