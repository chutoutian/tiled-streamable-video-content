# tiled-streamable-video-content

## 编译 Kvazaar

### 下载[Kvazaar](https://github.com/ultravideo/kvazaar#compiling-kvazaar)工程

安装Homebrew
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
