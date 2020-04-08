# 🤖 Model Bilgileri

## 🌱 Genel Bilgi

| 🔎 Model adı |  SSD Mobilenet V1 Quantized COCO |
| :--- | :--- |
| 🔸 Tanıdığı nesneler | [Burada](https://github.com/asmaamirkhan/CocukAsistan-AI/blob/master/nesneler.md) |
| 👨‍🔧 `.config` dosyası | [Burada](https://github.com/asmaamirkhan/CocukAsistan-AI/blob/master/Karma/ssd_mobilenet_v1_quantized_300x300_coco14_sync.config) |
| 🏷️ `label_map` dosyası | [Burada](https://github.com/asmaamirkhan/CocukAsistan-AI/blob/master/Karma/label_map.pbtxt) |
| 🤖 `.tflite` dosyası | [Burada](https://github.com/asmaamirkhan/CocukAsistan-AI/tree/master/Model/tflite) |

## 👮‍♂️ Giriş Çıkış Bilgileri

### 👨‍💻 Elde etme scripti

```python
import tensorflow as tf

interpreter = tf.lite.Interpreter(model_path="ssd_quant_v1_25.tflite")
interpreter.allocate_tensors()

# Print input shape and type
print(interpreter.get_input_details()[0]['shape'])
print(interpreter.get_input_details()[0]['dtype'])

# Print output shape and type
print(interpreter.get_output_details()[0]['shape'])
print(interpreter.get_output_details()[0]['dtype'])
```

### 🚪 Çıktı

#### 📥 Giriş Bilgileri

```python
# giriş boyutu
[  1 300 300   3]

# giriş türü 
<class 'numpy.uint8'>
```

#### 📤 Çıkış Bilgileri

```python
# çıkış boyutu
[ 1 10  4]

# çıkış türü
<class 'numpy.float32'>
```

