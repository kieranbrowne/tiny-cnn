# Tiny CNN

Experimentation to reduce cnn weights

## installation
```
conda env create
source activate tf-3
```

## Check if gpus available
```python
from tensorflow.python.client import device_lib
local_device_protos = device_lib.list_local_devices()
[x.name for x in local_device_protos if x.device_type == 'GPU']
```

## GPU debugging
- Needed to exclude the old GTXs with `export CUDA_VISIBLE_DEVICES=0,1,2`
- Needed to drop the amount of memory used by tf with:
  ```python
  gpu_options = tf.GPUOptions(per_process_gpu_memory_fraction=0.333)
  sess = tf.Session(config=tf.ConfigProto(gpu_options=gpu_options))
  ```
- You can kill processes which are wasting gpu space by using `nvidia-smi` to find the PIDs and then kill them with `kill -9 <PID>`
