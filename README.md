# Video Converter - 视频压缩工具

基于 PyQt6 + FFmpeg 的视频批量压缩工具，支持多种编码器和硬件加速。

## 功能特性

### 核心功能

- **批量扫描** - 递归扫描文件夹中的所有视频文件
- **多线程分析** - 4线程并行分析视频信息，加速扫描
- **智能压缩评分** - 根据编码、码率、体积自动评估压缩价值
- **多编码器支持** - libx264、libx265、VP9、AV1
- **硬件加速** - NVIDIA NVENC、Intel QSV 硬件编码
- **两遍编码** - 支持 x264/x265 两遍编码，提升压缩质量

### 操作功能

- **拖拽导入** - 直接拖拽视频文件或文件夹到窗口
- **导入/加载列表** - 支持 JSON 格式的视频列表导入导出
- **输出格式选择** - MP4 或 MKV
- **自定义输出目录** - 可指定压缩后文件的保存位置
- **暂停/继续/停止** - 压缩过程中可随时控制
- **删除源文件** - 压缩成功后自动删除源文件
- **自动关机** - 全部压缩完成后自动关机

### 界面

- 深色表头 + 简洁配色
- 实时进度显示（单文件 + 总体）
- 压缩日志对话框

## 环境要求

- Python 3.9+
- FFmpeg（需添加到系统 PATH）

## 安装

```bash
git clone https://github.com/yourusername/video_converter.git
cd video_converter
pip install -r requirements.txt
```

## 使用

```bash
python videomanager.py
```

### 操作流程

1. 点击 **"扫描文件夹"** 或 **拖拽文件** 到窗口
2. 在表格中勾选要压缩的视频
3. 选择编码器、CRF 值、输出格式
4. 点击 **"压缩选中"** 开始压缩

### 编码器说明

| 编码器     | 速度 | 压缩率 | 说明            |
| ---------- | ---- | ------ | --------------- |
| libx264    | 快   | 中     | 兼容性最好      |
| libx265    | 慢   | 高     | 新一代编码      |
| libvpx-vp9 | 中   | 高     | WebM 格式       |
| libaom-av1 | 很慢 | 很高   | 下一代标准      |
| h264_nvenc | 很快 | 中     | NVIDIA 显卡加速 |
| hevc_nvenc | 快   | 高     | NVIDIA 显卡加速 |
| h264_qsv   | 很快 | 中     | Intel 核显加速  |
| hevc_qsv   | 快   | 高     | Intel 核显加速  |

### CRF 值参考

- **18-22** - 高质量，文件较大
- **23-28** - 平衡质量与大小（推荐）
- **29-35** - 中等质量，文件较小

## 文件说明

```
videomanager.py    # 主程序
config.json        # 视频信息缓存（自动生成）
requirements.txt   # 依赖列表
```

## 截图

<img width="1102" height="632" alt="image" src="https://github.com/user-attachments/assets/c22b2d81-cd66-49e2-b394-7bd46b8dd714" />
<img width="1102" height="632" alt="image" src="https://github.com/user-attachments/assets/f596d0e3-4534-4365-85ad-139caae22e27" />


## 许可证

MIT License
