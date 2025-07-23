# PLC Data Format Converter & Debugger

[English](#english) | [中文](#中文)

---

## English

A pure frontend web tool designed for **PLC data format conversion and debugging**. This tool helps engineers test various combinations of PLC byte order, data types, and encoding formats to identify the actual meaning of raw data.

### 🎯 Purpose

This tool focuses solely on local memory data format conversion, arrangement, combination, and output - no PLC communication required. Perfect for debugging and understanding PLC data formats across different manufacturers and protocols.

### ⭐ Key Features

#### 🔧 Basic Functions
- **Raw Data Input Support**
  - Support for `byte[]` and `ushort[]` format input
  - Example inputs:
    - `byte[]`: `[0x01, 0x00, 0x00, 0x00]`
    - `ushort[]`: `[256, 0, 512, 1]`
  - Flexible input parsing (comma, space, newline separated)

- **Input Mode Selection**
  - Support for multiple data type arrays: `bool`, `byte`, `sbyte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`
  - Input validation with format compatibility checking
  - User-friendly error messages for invalid format combinations

#### 🔄 Advanced Core Functions
- **Automatic Combination Traversal**
  - **Byte Order Arrangements:**
    - ABCD (Big Endian)
    - DCBA (Little Endian) 
    - CDAB (Siemens Common)
    - BADC (Omron Common)
  
  - **Encoding Formats:**
    - DEC (Standard Decimal)
    - BCD (Binary Coded Decimal - each nibble 0~9)
    - HEX (Hexadecimal Direct)
  
  - **Data Type Support:**
    - ✅ Boolean: `bool` (bit)
    - ✅ Integers: `byte`, `sbyte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`
    - ✅ Floating Point: `float`, `double`
    - ✅ Strings: `ASCII` (fixed length), `UTF-8` (optional)

#### 🔍 Detailed Conversion Mode
- **Single Combination Selection**
  - Choose specific data type (e.g., int32)
  - Select byte order (e.g., CDAB)
  - Pick encoding method (e.g., BCD)
  
- **Step-by-Step Process Display**
  - Detailed calculation explanation
  - Raw data transformation at each stage
  - Byte position and order visualization
  - Intermediate hex, decimal, and binary display

#### ✨ Enhanced Features
- **Error Detection & Validation**
  - BCD format validation (0~9 per nibble)
  - IEEE-754 floating point validation
  - Anomaly highlighting (extreme values)

- **Result Organization**
  - Sort by data type, byte order, or encoding
  - Quick filtering and grouping
  - Smart result highlighting

- **Copy & Export**
  - One-click copy for all results
  - Multiple format support (raw, decimal, hex, string)

- **Device Reference Guide**
  - Common PLC brand byte order defaults
  - Encoding convention explanations
  - Manufacturer-specific presets

### 🚀 Getting Started

1. **Input your raw data** in the supported format
2. **Select input type** (byte array, ushort array, etc.)
3. **Choose conversion mode:**
   - **Auto Mode**: View all possible combinations
   - **Manual Mode**: Select specific type/order/encoding
4. **Analyze results** and copy the correct interpretation

### 📱 User Interface

- **Data Input Panel**: Raw data entry with format selection
- **Control Options**: Type, byte order, and encoding selectors  
- **Results Display**: All combination results with highlighting
- **Detail Viewer**: Step-by-step conversion explanation

### 🛠️ Technical Stack

- **Frontend Only**: No backend dependencies
- **Technologies**: HTML5, JavaScript (ES6+), CSS3
- **Performance**: Web Worker support for heavy calculations
- **Compatibility**: Modern browsers (Chrome, Firefox, Safari, Edge)

### 📋 Planned Features

#### 🧩 Universal Data Conversion
- [x] Multiple input formats (byte[], ushort[], HEX)
- [x] All byte order combinations  
- [x] Endianness switching
- [x] Common data type parsing
- [x] Detailed conversion explanations
- [x] Bilingual support (EN/CN)

#### 📐 Advanced Format Support
- [x] BCD format parsing
- [x] DEC encoding recognition  
- [x] ASCII/String decoding
- [ ] Timestamp conversion
- [ ] Custom encoding formats

#### 🔁 Bidirectional Conversion  
- [x] Type → Byte[] conversion
- [x] Byte[] → All types parsing
- [ ] Custom byte order reverse calculation

#### 🧠 Smart Analysis Tools
- [x] Auto-try all combinations
- [x] Format detection (BCD/DEC/ASCII)
- [ ] Intelligent type suggestions
- [ ] Pattern recognition

#### 📡 Protocol/Embedded Features
- [ ] Modbus CRC16 calculation
- [ ] Modbus frame constructor  
- [ ] Address conversion tools
- [ ] Bit visualization
- [ ] Brand-specific presets
- [ ] Floating point simulator

### 🤝 Contributing

Contributions are welcome! Please feel free to submit issues, feature requests, or pull requests.

### 📄 License

This project is open source. Please check the LICENSE file for details.

---

## 中文

一个专为 **PLC 数据格式转换与调试** 设计的纯前端网页工具。该工具帮助工程师测试各种 PLC 字节序、数据类型、编码格式的所有组合，以识别原始数据的实际含义。

### 🎯 工具目标

本工具专注于本地内存数据格式转换、排列、组合、输出，无需 PLC 通信功能。非常适合调试和理解不同制造商和协议的 PLC 数据格式。

### ⭐ 核心功能

#### 🔧 基础功能
- **原始数据输入支持**
  - 支持 `byte[]` 和 `ushort[]` 格式输入
  - 输入示例：
    - `byte[]`：`[0x01, 0x00, 0x00, 0x00]`
    - `ushort[]`：`[256, 0, 512, 1]`
  - 灵活的输入解析（逗号、空格、换行分隔）

- **输入模式选择**
  - 支持多种数据类型数组：`bool`、`byte`、`sbyte`、`short`、`ushort`、`int`、`uint`、`long`、`ulong`、`float`、`double`
  - 输入验证与格式兼容性检查
  - 友好的无效格式组合错误提示

#### 🔄 高级核心功能
- **自动遍历所有组合**
  - **字节序排列：**
    - ABCD（大端）
    - DCBA（小端）
    - CDAB（西门子常见）
    - BADC（欧姆龙常见）
  
  - **编码格式：**
    - DEC（普通十进制编码）
    - BCD（每个半字节 0~9）
    - HEX（十六进制直接转换）
  
  - **数据类型支持：**
    - ✅ 布尔类：`bool`（bit）
    - ✅ 整数类：`byte`、`sbyte`、`short`、`ushort`、`int`、`uint`、`long`、`ulong`
    - ✅ 浮点类：`float`、`double`
    - ✅ 字符串：`ASCII`（固定长度）、`UTF-8`（可选）

#### 🔍 单独转换模式
- **单一组合选择**
  - 选择特定数据类型（如 int32）
  - 选择字节顺序（如 CDAB）
  - 选择编码方式（如 BCD）
  
- **详细计算过程显示**
  - 详细计算解释
  - 原始数据在每个阶段的变化
  - 字节位置和顺序可视化
  - 中间十六进制、十进制和二进制显示

#### ✨ 增强功能
- **错误检测与验证**
  - BCD 格式验证（每位 0~9）
  - IEEE-754 浮点验证
  - 异常值高亮显示

- **结果组织**
  - 按数据类型、字节顺序或编码排序
  - 快速过滤和分组
  - 智能结果高亮

- **复制与导出**
  - 所有结果一键复制
  - 多格式支持（原始、十进制、十六进制、字符串）

- **设备参考指南**
  - 常见 PLC 品牌字节序默认值
  - 编码约定说明
  - 制造商特定预设

### 🚀 快速开始

1. **输入原始数据**，支持多种格式
2. **选择输入类型**（字节数组、无符号短整型数组等）
3. **选择转换模式：**
   - **自动模式**：查看所有可能的组合
   - **手动模式**：选择特定类型/顺序/编码
4. **分析结果**并复制正确的解释

### 📱 用户界面

- **数据输入面板**：原始数据输入与格式选择
- **控制选项**：类型、字节顺序和编码选择器
- **结果显示**：所有组合结果与高亮显示
- **详细查看器**：逐步转换解释

### 🛠️ 技术栈

- **纯前端**：无后端依赖
- **技术**：HTML5、JavaScript (ES6+)、CSS3
- **性能**：支持 Web Worker 进行重计算
- **兼容性**：现代浏览器（Chrome、Firefox、Safari、Edge）

### 📋 计划功能

#### 🧩 通用数据转换
- [x] 多种输入格式（byte[]、ushort[]、HEX）
- [x] 所有字节顺序组合
- [x] 大小端切换
- [x] 常用数据类型解析
- [x] 详细转换解释
- [x] 双语支持（中英文）

#### 📐 进阶格式支持
- [x] BCD 格式解析
- [x] DEC 编码识别
- [x] ASCII/字符串解码
- [ ] 时间戳转换
- [ ] 自定义编码格式

#### 🔁 可逆转换功能
- [x] 类型 → Byte[] 转换
- [x] Byte[] → 所有类型解析
- [ ] 自定义字节顺序逆向计算

#### 🧠 智能分析工具
- [x] 自动尝试所有组合
- [x] 格式检测（BCD/DEC/ASCII）
- [ ] 智能类型建议
- [ ] 模式识别

#### 📡 协议/嵌入式功能
- [ ] Modbus CRC16 计算
- [ ] Modbus 报文构造器
- [ ] 地址转换工具
- [ ] 位可视化
- [ ] 品牌特定预设
- [ ] 浮点数模拟器

### 🤝 贡献

欢迎贡献！请随时提交问题、功能请求或拉取请求。

### 📄 许可证

此项目为开源项目。详细信息请查看 LICENSE 文件。
