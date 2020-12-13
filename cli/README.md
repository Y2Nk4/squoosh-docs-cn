# Squoosh CLI

Squoosh CLI 是一个 _实验性的_ ，允许你使用WebAssembly在命令行上运行所有在 [Squoosh] 网页上编码器的工具。
Squoosh CLI 使用 worker pool 来并行处理图片。这样，你就可以使用一个编码器同时处理多张图片。

Squoosh CLI目前不是，且不旨在成为市面上最快的图像压缩工具。但是它能足以快速地同时处理多张图片。

## 安装

The Squoosh CLI 可以通过 `npx` 在没有安装的情况下直接通过命令行运行:

```
$ npx @squoosh/cli <options...>
```

当然，你也可以通过安装运行 Squoosh CLI:

```
$ npm i -g @squoosh/cli
$ squoosh-cli <options...>
```

## 使用方法

```
Usage: squoosh-cli [options] <files...>

Options:
  -V, --version                                          输出版本号
  -d, --output-dir <dir>                                 输出目录 (默认: ".")
  -s, --suffix <suffix>                                  用于为输出文件名添加指定的后缀 (默认: "")
  --max-optimizer-rounds <rounds>                        用于自动优化的最大压缩次数 (默认: "6")
  --optimizer-butteraugli-target <butteraugli distance>  用于自动优化的目标 Butteraugli 距离 (默认: "1.4")
  --resize [config]                                      在压缩之前调整图像尺寸
  --quant [config]                                       减少图片中使用的颜色的数量 (aka. paletting)
  --rotate [config]                                      旋转图片
  --webp [config]                                        指定使用 WebP 生成 .webp 文件的配置
  --avif [config]                                        指定使用 AVIF 生成 .avif 文件的配置
  --jxl [config]                                         指定使用 JPEG-XL 生成 .jxl 文件的配置
  --wp2 [config]                                         指定使用 WebP2 生成 .wp2 文件的配置
  --oxipng [config]                                      指定使用 OxiPNG 生成 .png 文件的配置
  -h, --help                                             显示使用教程
```

每个 `config` 选项的默认值都可以在 [`codecs.js`][https://github.com/GoogleChromeLabs/squoosh/blob/dev/cli/src/codecs.js] 文件中的 `defaultEncoderOptions` 找到。
若值未指定，将会使用上述文件中的默认值。( _此处应有更好的文档_ )

## 自动优化器

Squoosh CLI具有一个 _实验性_ 的自动优化器用于尽可能地压缩图片，并不断尝试去达到特定的 [Butteraugli] 目标值。
Butteraugli 目标值越高，图片失真的程度越高。
你可以通过设置 `config` 的值为 `auto` 来使用自动优化器

```
$ npx @squoosh/cli --wp2 auto test.png
```

[squoosh]: https://squoosh.app
[codecs.js]: https://github.com/GoogleChromeLabs/squoosh/blob/dev/cli/src/codecs.js
[butteraugli]: https://github.com/google/butteraugli
