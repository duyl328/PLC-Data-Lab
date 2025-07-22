# PLC Data Lab

> A portable, zero-dependency, browser-based tool for analyzing and converting PLC raw data formats.

> 一个可在任意浏览器运行的、零依赖的 PLC 原始数据解析与转换工具。

---

## 🌟 项目简介 | Project Introduction

**PLC Data Lab** 是一个专为 PLC 通信开发者、自动化工程师、嵌入式工程人员设计的数据调试辅助工具。
通过浏览器即可运行，无需安装、无依赖，可进行 PLC 中常见数据格式的输入、转换、解释。

**PLC Data Lab** is designed for automation developers and PLC engineers who need to debug or analyze data formats in different PLCs. It works entirely in the browser and offers complete support for multiple byte orders, encodings, and data types.

---

## ✨ 核心特性 | Core Features

* ✅ 原始数据输入支持 byte\[] / ushort\[] / HEX 字符串
* 🔁 字节顺序排列组合：ABCD、BADC、CDAB、DCBA 全部支持
* 🔄 大端 / 小端切换（支持位序 / 字节序）
* 🔎 自动枚举所有组合，列出所有可能的解析结果
* 📚 类型支持广泛：bool, byte, short, ushort, int, uint, long, ulong, float, double, string, BCD, DEC 等
* 🔍 每种转换结果都带有详细的解释过程
* 📱 无需安装，浏览器即开即用（支持移动端）
* 🌐 支持常见 PLC 协议结构（欧姆龙、三菱、西门子、Modbus、AB 等）

---

## 📦 使用方法 | How to Use

1. 下载本项目或直接打开 [index.html](./index.html)
2. 粘贴你从 PLC 读到的原始数据（十六进制、byte 数组或 word 数组）
3. 选择数据排列方式（如 CDAB）和编码（如 BCD）
4. 查看自动生成的所有类型解析结果
5. 点击任意一个结果，可查看详细解释与转换路径

### 示例输入格式 | Sample Input

```text
Hex:        01 00 00 00
Byte[]:     [1, 0, 0, 0]
Ushort[]:   [1, 0]
```

---

## 🎯 使用场景 | Use Cases

* PLC 通信调试（西门子 / 欧姆龙 / 三菱 / AB 等）
* SCADA / MES 系统与 PLC 数据对接校验
* 工控培训教学 / 自学 PLC 数据结构
* 嵌入式系统 / Modbus 协议数据解析
* 快速判断未知数据编码方式

---

---

## 📄 License

MIT License © 2025-present PLCDataLab Contributors
