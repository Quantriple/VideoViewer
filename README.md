# Windows 视频快速阅览器

一个轻量级的 Windows 原生桌面应用，专门用于快速浏览和管理本地视频文件。

## 功能特性

- 🎬 **快速扫描**: 递归扫描目录，支持多种视频格式
- 📋 **文件列表**: 清晰显示视频文件信息（名称、大小、修改时间）
- ▶️ **一键播放**: 双击文件即可调用系统默认播放器
- 🗑️ **安全删除**: 支持将文件移动到回收站
- 🔍 **快速搜索**: 按文件名快速定位视频文件
- 🎯 **原生性能**: 使用 C++20 和 Win32 API，无额外依赖

## 支持的视频格式

- MP4 (.mp4)
- MKV (.mkv) 
- AVI (.avi)
- MOV (.mov)
- WMV (.wmv)
- FLV (.flv)
- WebM (.webm)

## 系统要求

- Windows 10/11 (x64)
- Visual C++ Redistributable (如果使用 MSVC 编译)

## 构建要求

- CMake 3.20+
- C++20 兼容编译器:
  - MSVC 2022+ (推荐)
  - MinGW-w64 15.1.0+
- Windows SDK

## 构建说明

### 使用 MSVC (推荐)

```bash
# 创建构建目录
mkdir build
cd build

# 配置项目
cmake .. -G "Visual Studio 17 2022" -A x64

# 编译
cmake --build . --config Release
```

### 使用 MinGW-w64

```bash
# 创建构建目录
mkdir build
cd build

# 配置项目
cmake .. -G "MinGW Makefiles"

# 编译
cmake --build . --config Release
```

## 使用说明

1. **启动程序**: 运行 `VideoViewer.exe`
2. **扫描目录**: 点击工具栏的"扫描"按钮，选择包含视频文件的目录
3. **浏览文件**: 在列表中查看扫描到的视频文件
4. **播放视频**: 双击文件名即可使用系统默认播放器播放
5. **删除文件**: 右键点击文件，选择"删除"将文件移动到回收站
6. **搜索文件**: 使用搜索框快速定位特定文件

## 项目结构

```
VideoViewer/
├── src/                    # 源代码目录
│   ├── main.cpp           # 程序入口
│   ├── MainWindow.cpp     # 主窗口实现
│   ├── FileScanner.cpp    # 文件扫描器
│   ├── VideoManager.cpp   # 视频管理器
│   ├── VideoFile.cpp      # 视频文件类
│   ├── Utils.cpp          # 工具函数
│   ├── DatabaseManager.cpp # 数据库管理
│   ├── VideoFileDAO.cpp   # 数据访问对象
│   └── ThumbGen.cpp       # 缩略图生成
├── include/               # 头文件目录
├── resources/             # 资源文件
│   ├── VideoViewer.rc     # Windows 资源文件
│   └── resource.h         # 资源头文件
├── third_party/           # 第三方库
│   └── sqlite/           # SQLite 数据库
├── CMakeLists.txt         # CMake 构建配置
└── README.md             # 项目说明
```

## 技术特性

- **原生 Windows API**: 使用 Win32 API 实现，性能优异
- **现代 C++**: 采用 C++20 标准，代码简洁高效
- **SQLite 数据库**: 本地数据库存储，支持快速检索
- **缩略图支持**: 自动生成视频缩略图（可选功能）
- **多线程扫描**: 异步文件扫描，界面响应流畅
- **中文支持**: 完整的中文界面和文件名支持

## 开发计划

- [ ] 视频缩略图预览
- [ ] 播放列表功能
- [ ] 视频信息详情显示
- [ ] 自定义播放器集成
- [ ] 批量操作功能
- [ ] 设置配置界面

## 许可证

本项目采用 MIT 许可证 - 查看 [LICENSE](LICENSE) 文件了解详情。

## 贡献

欢迎提交 Issue 和 Pull Request！

## 联系方式

如有问题或建议，请通过 GitHub Issues 联系。