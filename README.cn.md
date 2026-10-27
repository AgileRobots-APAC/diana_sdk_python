# diana_sdk_python

[English](README.md) | [中文](README.cn.md)

思灵机器人 Diana Python SDK 的独立仓库。当前内容为主 examples 仓库使用的 **3.3.0 Linux x86_64** Python 包；主 examples 仓库会以 Git submodule 的形式引用本仓库。

发布或共享本仓库前，请确认厂商 SDK 许可允许在目标私有仓库中保存和分发 SDK 封装、原生运行时库及保留的 PDF 文档。

需要升级 SDK 时，直接替换 `lib/`、`doc/` 和 `version` 中的 Python 内容，并以 SDK 版本号提交；`doc/` 只保留应随本 Python examples 仓库发布的文档，不要再增加版本子目录。

```text
diana_sdk_python/
├── lib/
│   ├── DianaApi.py
│   ├── libDianaApi.so
│   ├── libBasicSdk.so
│   ├── libGenericAlgorithm.so
│   ├── libToolSdk.so
│   ├── libVersionApi.so
│   └── libxml2.so
├── doc/
│   └── 思灵机器人工业版API手册（Python版）
└── version
```

在 examples 主仓库中以子模块形式使用时，从 `third_party/diana_sdk_python/lib` 导入 Python 封装。当前随仓库提供的原生库仅适用于 64 位 x86 Linux；其他操作系统或 CPU 架构必须改用厂商提供的对应版本。

临时运行脚本或示例时，先把封装目录加入 `PYTHONPATH`：

```bash
export PYTHONPATH="$PWD/third_party/diana_sdk_python/lib:$PYTHONPATH"
```

在 Linux 上运行时，还需要使动态链接器能找到 `lib/` 中的全部原生 SDK 依赖：

```bash
export LD_LIBRARY_PATH="$PWD/third_party/diana_sdk_python/lib:$LD_LIBRARY_PATH"
```
