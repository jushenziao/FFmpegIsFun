首先确认是否已经将 pkg-config工具安装好了。

这个工具建议搜下了解下

pkg-config 

如果提示没有安装，则先将该工具安装好，安装命令如下：

- ubuntu

apt intall pkg-config 

- mac

brew install pkg-config 

- cygwin

apt-cyg install pkg-config 

- centos

yum install pkg-config



**Mac OS X手动安装yasm（编译FFmpeg前置步骤）**



brew install yasm

https://www.jianshu.com/p/3733ae5a0243

https://superuser.com/questions/844683/how-to-install-yasm-1-2-0-and-compile-ffmpeg-library-on-mac



git clone https://git.ffmpeg.org/ffmpeg.git



./configure --prefix=/usr/local/ffmpeg --enable-gpl --enable-nonfree --enable-libfdk-aac --enable-libx264 --enable-libx265 --enable-filter=delogo --enable-debug --disable-optimizations --enable-libspeex --enable-videotoolbox  --enable-shared --enable-static --enable-pthreads --enable-version3 --enable-hardcoded-tables --cc=clang --host-cflags= --host-ldflags= 



**Mac OS编译ffmpeg出错 ERROR: libfdk_aac not found**

Mac OS编译ffmpeg出错ERROR: libfdk_aac not found，安装libfdk后解决

First Try -首先执行如下命令:

brew install fdk-aac 

Failing that you can compile like I do-然后执行如下操作：

git clone git://github.com/mstorsjo/fdk-aac cd fdk-aac autoreconf -i ./configure make install





**ERROR: speex not found using pkg-config**

**brew install speex**

**brew install x264**

**brew install x265**



sudo make install 

然后打开 cd /usr/local/ffmpeg/ 可以看到bin  include lib share

 cd bin 里面有ffmpeg ffplay ffprobe

ffmepg编译完成后会把*pc文件放在 usr/local/ffmpeg/pkgconfig文件夹下 需要配知道PKG_CONFIG_PATH