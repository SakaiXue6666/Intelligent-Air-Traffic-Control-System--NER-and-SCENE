# 📘 **智能空管系统（Intelligent Air Traffic Management System）**

本项目包含两个核心任务：

1. **实体命名识别（NER）**：提取航班号、机场、地点等关键字段
2. **场景识别（Scene Classification）**：识别飞行场景、状态类型等类别

系统整体用于构建基础的空管文本理解模块。

------

## 🚀 **项目结构与说明**

### **1. 实体命名识别（NER）训练**

使用 GlobalPointer + CLIP 编码器的结构，支持航班文本的实体抽取。

训练脚本：

```
train_clip_qk_fly_arg_onlyner.py
```

模型结构：

```
models/GlobalPointer_clip_qk_fly_arg.py
```

------

### **2. 场景识别（Scene Classification）训练**

使用 Qwen 语言模型作为分类 backbone，支持识别飞行状态/场景类别。

训练脚本：

```
train_qwen_fly_scene.py
```

模型结构：

```
models/Qwen_fly_scene_2_ner.py
```

------

### **3. 联合测试（NER + Scene）**

用于评估 NER + Scene 模型的联合推理能力。

测试脚本：

```
evaluate_fly_inter_GlobalNer_QwenCls.py
```

------

## 📦 **模型权重**

预训练模型放在：

```
pretrained_models/
```

训练后的结果权重、日志输出放在：

```
outputs/
```

------

## ⚙️ **模型配置**

所有训练/测试的配置文件存放于：

```
config_fly/
```

包含超参数设置、模型路径、训练策略等。

------

## 🛠️ **工具函数**

常用数据预处理、lowercase 工具等位于：

```
common/utils_lower.py
```
