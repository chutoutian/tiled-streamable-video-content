# tiled-streamable-video-content

## 编译 Kvazaar

### 下载[Kvazaar](https://github.com/ultravideo/kvazaar#compiling-kvazaar)工程

1、安装Homebrew

2、编译Kvazaar
```
brew install automake libtool yasm

./autogen.sh

./configure

make

sudo make install

```
 
### 将视频编码并分片
```
$ kvazaar -i input.yuv --input-res 3840x2160 -o output.hvc --tiles 3x3 --slices tiles --mv-constraint frametilemargin -q 30 --period 30 --input-fps 30

```
其中 3840x2160 是原生视频的分辨率 

### 一些参数
```
Usage:
kvazaar -i <input> --input-res <width>x<height> -o <output>

Required:
  -i, --input <filename>     : Input file
      --input-res <res>      : Input resolution [auto]
                                   - auto: Detect from file name.
                                   - <int>x<int>: width times height
  -o, --output <filename>    : Output file

Parallel processing:
  --tiles <int>x<int>    : Split picture into width x height uniform tiles.
      --tiles-width-split <string>|u<int> :
                                   - <string>: A comma-separated list of tile
                                               column pixel coordinates.
                                   - u<int>: Number of tile columns of uniform
                                             width.
      --tiles-height-split <string>|u<int> :
                                   - <string>: A comma-separated list of tile row
                                               column pixel coordinates.
                                   - u<int>: Number of tile rows of uniform
                                             height.
      --slices <string>      : Control how slices are used.
                                   - tiles: Put tiles in independent slices.
                                   - wpp: Put rows in dependent slices.
                                   - tiles+wpp: Do both.

```

