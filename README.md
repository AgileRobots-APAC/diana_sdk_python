# diana_sdk_python

[English](README.md) | [中文](README.cn.md)

Standalone repository for the Siasun Diana Python SDK. The current contents are the **3.4.0 Linux x86_64** Python package used by this examples repository. The main examples repository references this repository as a Git submodule.

Before publishing or sharing this repository, confirm that the vendor SDK license allows the target private repository to store and distribute the SDK wrapper, native runtime libraries, and retained PDF documentation.

To upgrade the SDK, replace the Python contents of `lib/`, `doc/`, and `version`, then commit with the SDK version number. Keep `doc/` limited to documentation that should ship with this Python examples repository, and do not add nested version directories.

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
│   └── Siasun Diana industrial robot API manual (Python edition)
└── version
```

When used as a submodule from the main examples repository, import the wrapper from `third_party/diana_sdk_python/lib`. The bundled native libraries are for 64-bit x86 Linux only. Use a vendor package matching the target operating system and CPU architecture on other platforms.

For ad hoc scripts, add the wrapper directory to `PYTHONPATH` before running examples from the main repository:

```bash
export PYTHONPATH="$PWD/third_party/diana_sdk_python/lib:$PYTHONPATH"
```

On Linux, also make the dynamic linker able to find all native SDK dependencies in `lib/`:

```bash
export LD_LIBRARY_PATH="$PWD/third_party/diana_sdk_python/lib:$LD_LIBRARY_PATH"
```
