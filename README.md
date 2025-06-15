# PPT内容提取器 / PPT Content Extractor

一款简易实用的桌面工具，支持"一键提取"PPT文件中的文本、图片、视频等内容。

A simple and practical desktop tool that supports "one-click extraction" of text, images, videos and other content from PPT files.

## 功能特性 / Features

### 🎯 核心功能 / Core Functions
- **提取文字（分页）** - 每页生成单独TXT文件 / Extract text (per slide) - Generate separate TXT files for each slide
- **提取文字（汇总）** - 全部文字合并为一个TXT文件 / Extract text (combined) - Merge all text into one TXT file  
- **提取图视频** - 批量导出所有图片和视频文件 / Extract media - Batch export all images and video files
- **一键提取** - 同时执行文字汇总和图视频提取 / One-click extract - Execute text summary and media extraction simultaneously

### 🚀 操作特性 / Operation Features
- **拖拽支持** - 支持直接拖拽PPT文件到软件界面 / Drag & Drop - Support dragging PPT files directly to the software interface
- **批量处理** - 可同时处理多个PPT文件 / Batch Processing - Can process multiple PPT files simultaneously
- **进度显示** - 实时显示处理进度和状态 / Progress Display - Real-time display of processing progress and status
- **日志记录** - 详细的操作日志和错误提示 / Logging - Detailed operation logs and error prompts

## 系统要求 / System Requirements

- **操作系统 / OS**: Windows 10+ 
- **Python**: 3.8+
- **依赖库 / Dependencies**: PyQt6, python-pptx, Pillow

## 安装使用 / Installation & Usage

### 方法一：直接运行源码 / Method 1: Run Source Code Directly

1. **克隆项目 / Clone Project**
   ```bash
   git clone <repository-url>
   cd ppt-extractor
   ```

2. **安装依赖 / Install Dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **运行程序 / Run Program**
   ```bash
   python main.py
   ```

### 方法二：打包为可执行文件 / Method 2: Package as Executable

1. **安装打包工具 / Install Packaging Tool**
   ```bash
   pip install pyinstaller
   ```

2. **打包程序 / Package Program**
   ```bash
   pyinstaller --onefile --windowed --name="PPT内容提取器" main.py
   ```

3. **运行可执行文件 / Run Executable**
   - 在 `dist` 目录中找到生成的可执行文件 / Find the generated executable in the `dist` directory

## 使用说明 / Usage Instructions

### 基本操作流程 / Basic Operation Flow

1. **添加文件 / Add Files**
   - 拖拽PPT文件到软件界面 / Drag PPT files to the software interface
   - 或点击"选择PPT文件"按钮 / Or click the "Select PPT Files" button

2. **选择功能 / Select Function**
   - 选择需要的提取模式 / Select the desired extraction mode
   - 默认为"一键提取"模式 / Default is "One-click Extract" mode

3. **设置输出 / Set Output**
   - 默认输出到桌面的"PPT提取结果"文件夹 / Default output to "PPT Extract Results" folder on desktop
   - 可点击"更改目录"自定义输出位置 / Click "Change Directory" to customize output location

4. **开始提取 / Start Extraction**
   - 点击"开始提取"按钮 / Click the "Start Extraction" button
   - 查看进度条和日志信息 / View progress bar and log information

5. **查看结果 / View Results**
   - 提取完成后会弹出提示 / A prompt will appear after extraction is complete
   - 点击"打开输出目录"查看结果 / Click "Open Output Directory" to view results

### 输出文件结构 / Output File Structure

```
PPT提取结果/
├── PPT文件名1/
│   ├── slide_1.txt          # 分页文字提取
│   ├── slide_2.txt
│   ├── all_text.txt         # 汇总文字提取
│   ├── image1.png           # 图片文件
│   ├── image2.jpg
│   └── video1.mp4           # 视频文件
└── PPT文件名2/
    └── ...
```

## 支持格式 / Supported Formats

### 输入格式 / Input Formats
- **.pptx** - PowerPoint 2007及以上版本 / PowerPoint 2007 and above
- **.ppt** - PowerPoint 97-2003版本（仅文字提取）/ PowerPoint 97-2003 (text extraction only)

### 输出格式 / Output Formats
- **文本文件**: UTF-8编码的TXT文件 / Text files: UTF-8 encoded TXT files
- **图片文件**: PNG, JPG, JPEG, GIF, BMP, TIFF
- **视频文件**: MP4, AVI, MOV, WMV
- **音频文件**: MP3, WAV, M4A

## 项目结构 / Project Structure

```
ppt-extractor/
├── main.py                  # 程序入口 / Program entry point
├── requirements.txt         # 依赖列表 / Dependencies list
├── README.md               # 说明文档 / Documentation
├── core/                   # 核心功能模块 / Core functionality modules
│   ├── __init__.py
│   └── extractor.py        # PPT提取引擎 / PPT extraction engine
├── gui/                    # 图形界面模块 / GUI modules
│   ├── __init__.py
│   ├── main_window.py      # 主窗口 / Main window
│   └── widgets.py          # 自定义组件 / Custom widgets
└── 需求文档.md              # 产品需求文档 / Product requirements document
```

## 技术实现 / Technical Implementation

- **GUI框架**: PyQt6 - 跨平台图形界面框架 / Cross-platform GUI framework
- **PPT解析**: python-pptx - PowerPoint文件解析库 / PowerPoint file parsing library
- **多线程**: QThread - 后台处理避免界面卡顿 / Background processing to avoid UI freezing
- **文件处理**: zipfile, pathlib - 文件操作和路径处理 / File operations and path handling

## 常见问题 / FAQ

### Q: 为什么.ppt文件无法提取图片？
A: .ppt是旧版格式，建议先转换为.pptx格式再进行图片提取。

### Q: Why can't .ppt files extract images?
A: .ppt is an old format. It's recommended to convert to .pptx format first for image extraction.

### Q: 提取的文字出现乱码怎么办？
A: 程序使用UTF-8编码保存文件，请使用支持UTF-8的文本编辑器打开。

### Q: What to do if extracted text appears garbled?
A: The program saves files using UTF-8 encoding. Please use a text editor that supports UTF-8.

### Q: 可以处理多大的PPT文件？
A: 理论上没有大小限制，但建议单个文件不超过100MB以确保处理速度。

### Q: What's the maximum PPT file size that can be processed?
A: There's no theoretical size limit, but it's recommended to keep individual files under 100MB for optimal processing speed.

## 更新日志 / Changelog

### v1.0.0 (2024-01-XX)
- ✨ 初始版本发布 / Initial version release
- 🎯 支持四种提取模式 / Support for four extraction modes
- 🖱️ 拖拽文件支持 / Drag and drop file support
- 📊 进度显示和日志记录 / Progress display and logging
- 🎨 现代化UI设计 / Modern UI design

## 许可证 / License

MIT License - 详见LICENSE文件 / See LICENSE file for details

## 贡献 / Contributing

欢迎提交Issue和Pull Request！/ Welcome to submit Issues and Pull Requests!

## 联系方式 / Contact

如有问题或建议，请通过以下方式联系：/ For questions or suggestions, please contact via:
- GitHub Issues
- Email: [your-email@example.com] 