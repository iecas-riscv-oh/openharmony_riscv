# gflags
## 简介

> gflags 包含一个实现命令行标志处理的 C++ 库。 它包括对标准类型（如字符串）的内置支持以及在使用它们的源文件中定义标志的能力。

## 下载安装
直接在OpenHarmony-SIG仓中搜索gflags并下载。

## 使用说明
以OpenHarmony 3.0 和全志D1开发板为例

1. 库代码存放路径：./third_party/gflags

2. 修改添加依赖的编译脚本，路径：/build/common/BUILD.gn

```
    import("//build/config/ohos/config.gni")
    import("//build/config/sanitizers/sanitizers.gni")
    import("//build/ohos.gni")
    
    group("common_packages") {
      deps = []
      deps += [
        "//third_party/giflib:libgif",
        "//third_party/libpng:libpng",
        "//third_party/sqlite:sqlite",
        "//third_party/zlib:libz",
        "//third_party/gflags:gflags",
        # "//third_party/gflags:gflags_strip_flags_test",
      ]
    
      deps += [ "musl:musl_install" ]
    
      if (is_asan) {
        deps += [
          "asan:asan.options",
          "asan:libclang_rt.asan.so",
        ]
      }
    }
```

3. 用命令 ./build.sh --product-name sunxi_d1 --ccache 编译



