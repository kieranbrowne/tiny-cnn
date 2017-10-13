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
