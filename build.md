# 编译boost

## 需求

- 使用github actions编译boost
- 平台 msvc(x86_64) llvm-mingw(windowsx86_64) gcc(x86_64/arm) llvm(x86_64/arm)
- 需要静态编译boost的所有组件
- boost github源码是多个子仓库构成 建议直接使用release中的完整的源码压缩包
- 需要使用带cmake后缀的压缩包 比如`boost-1.92.0-cmake`
- 编译最新正式版本 需要添加任务每天检查是否有最新版本 如果有就编译
- 结果需要上传到release中
- 完成后还需要完善readme.md文档

## 注意

- actions的时间可能很长,你必须等待其完成后并检查日志其结果是否正确
- 然后根据结果来调正脚本
