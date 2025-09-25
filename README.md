# 中药材智能识别系统

## 项目简介

中药材智能识别系统是一个基于深度学习的桌面应用程序，能够通过上传中药材图片自动识别药材种类。该系统采用PyQt5构建用户界面，使用ResNet深度学习框架进行图像分类，支持超过30种中药材的识别。

## 功能特点

- **用户友好的图形界面**：简洁直观的桌面应用，操作简单
- **高精度识别**：基于深度学习模型，支持30+种中药材的精确识别
- **实时结果显示**：显示识别结果及置信度
- **多平台支持**：可在Windows、macOS和Linux等操作系统上运行
- **响应式设计**：界面自适应不同屏幕尺寸

## 环境要求

- Python 3.6+
- PyQt5
- PaddlePaddle 2.0+
- 其他依赖包：numpy, opencv-python, pillow等

## 安装步骤

1. 克隆项目到本地：
   ```bash
   git clone [项目仓库地址]
   cd medicine2
   ```

2. 创建并激活虚拟环境（推荐）：
   ```bash
   python -m venv venv
   source venv/bin/activate  # Linux/macOS
   .\venv\Scripts\activate  # Windows
   ```

3. 安装依赖：
   ```bash
   pip install -r requirements.txt
   ```
   
   如果尚未生成requirements.txt，可以手动安装主要依赖：
   ```bash
   pip install PyQt5 paddlepaddle opencv-python pillow numpy
   ```

## 项目结构

```
medicine2/
├── models/                  # 预训练模型文件
│   ├── inference.pdmodel    # 模型结构文件
│   └── inference.pdiparams  # 模型权重文件
├── json/                    # 标签文件
│   └── label.json           # 中药材标签映射
├── images/                  # 示例图片目录
├── logo/                    # 应用图标
├── ImageDetection.py        # 图像检测线程
├── defines.py               # 中药材定义
├── image.py                 # 图像处理工具
├── loginUnit.py             # 登录界面
├── loginUnit.ui             # 登录界面UI文件
├── main.py                  # 主程序入口
├── mainUnit.py              # 主界面
├── mainUnit.ui              # 主界面UI文件
├── predict.py               # 预测模块
└── README.md                # 项目说明文档
```

## 使用说明

1. 运行程序：
   ```bash
   python main.py
   ```

2. 登录界面：
   - 输入用户名（任意）
   - 点击"登录"按钮进入主界面
   - 或点击"注册"按钮注册新用户

3. 主界面操作：
   - 点击"导入图片"按钮选择中药材图片
   - 点击"开始检测"按钮进行识别
   - 查看右侧结果区域显示的识别结果和置信度
   - 检测历史记录显示在下方文本框中

## 技术细节

- **图像处理**：使用OpenCV和Pillow进行图像预处理
- **深度学习模型**：基于PaddlePaddle的预训练模型
- **多线程处理**：使用QThread实现异步图像处理，避免界面卡顿
- **UI设计**：使用Qt Designer设计，支持高DPI显示

## 模型训练

本项目使用PaddleClas进行模型训练，具体步骤如下：

1. 准备数据集：
   - 收集不同种类的中药材图片
   - 按照类别整理到不同文件夹
   - 生成训练集和验证集列表

2. 训练配置：
   - 修改配置文件中的数据集路径
   - 调整超参数（学习率、batch size等）
   - 选择预训练模型

3. 开始训练：
   ```bash
   python tools/train.py -c configs/your_config.yml
   ```

4. 模型导出：
   ```bash
   python tools/export_model.py -c configs/your_config.yml -o Global.pretrained_model=output/your_model/best_model
   ```

## 性能优化

- 使用OpenCV的DNN模块加速推理
- 实现模型预热，减少首次预测延迟
- 使用多线程处理耗时操作
- 优化图像预处理流程

## 常见问题

1. **程序无法启动**
   - 检查Python版本是否为3.6+
   - 确认所有依赖包已正确安装
   - 检查模型文件是否存在

2. **识别准确率低**
   - 确保拍摄的药材图片清晰
   - 尝试调整拍摄角度和光线
   - 检查模型是否需要更新

3. **运行速度慢**
   - 关闭其他占用GPU资源的程序
   - 降低图像分辨率
   - 考虑使用更高性能的硬件

## 贡献指南

欢迎提交Issue和Pull Request。提交代码前请确保：

1. 代码符合PEP 8规范
2. 添加必要的注释和文档
3. 更新测试用例
4. 通过所有测试

## 许可证



##完整项目代码获取请联系qq：2122384040



<img width="1257" height="860" alt="c8c033134a6d56531298246eb875c3d7" src="https://github.com/user-attachments/assets/7ff5168c-bc16-4bb6-bf69-f37ab5739231" />


