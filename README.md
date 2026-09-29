# Build Boost

使用 GitHub Actions 自动编译 boost 静态库，支持多平台多编译器。

## 支持的平台

| 平台 | 编译器 | 架构 |
|------|--------|------|
| Windows | MSVC | x86_64 |
| Windows | llvm-mingw | x86_64 |
| Linux | GCC | x86_64 |
| Linux | GCC | ARM64 |
| Linux | LLVM/Clang | x86_64 |
| Linux | LLVM/Clang | ARM64 |

## 编译产物

- 静态库 (`.lib` / `.a`)，不包含动态库
- boost 所有组件
- 基于 `boost-X.Y.Z-cmake` 源码包编译

## 使用方式

### 手动触发

在 GitHub Actions 页面点击 "Build Boost" workflow → "Run workflow"。

### 自动检查

每天 UTC 0:00 自动检查 boostorg/boost 是否有新版本发布，有则自动编译并上传到 Release。

## 下载

前往 [Releases](https://github.com/${{ github.repository }}/releases) 页面下载对应平台的预编译包。

每个压缩包包含 `include/` 和 `lib/` 目录，解压后可直接配置 cmake 使用：

```cmake
set(BOOST_ROOT /path/to/boost-install)
find_package(Boost REQUIRED)
target_link_libraries(your_target PRIVATE Boost::boost ...)
```

## 仓库结构

```
.
├── .github/workflows/build-boost.yml  # Actions 工作流
└── README.md
```