+ http://hg.openjdk.java.net/jdk9/

+ mac下编译openjdk1.9及集成clion动态调试:<https://www.jianshu.com/p/ee7e9176632c>

+ chmod +x configure

+ ./configure --with-target-bits=64 --with-freetype=/usr/local/Cellar/freetype/2.9.1 --enable-ccache --with-jvm-variants=server,client --with-boot-jdk-jvmargs="-Xlint:deprecation -Xlint:unchecked" --disable-zip-debug-info --disable-warnings-as-errors --with-debug-level=slowdebug 2>&1 | tee configure_mac_x64.log

+ WARNING: Option --enable-zip-debug-info is deprecated and will be ignored.
WARNING: Please use --with-native-debug-symbols=zipped .

+ sudo ./configure --with-target-bits=64 --with-freetype=/usr/local/Cellar/freetype/2.9.1 --enable-ccache --with-jvm-variants=server,client --with-boot-jdk-jvmargs="-Xlint:deprecation -Xlint:unchecked" --with-native-debug-symbols=zipped --disable-warnings-as-errors --with-debug-level=slowdebug 2>&1 | tee configure_mac_x64.log

+ sudo ./configure --enable-debug --with-jvm-variants=server (用这个！！！)

+ 重跑前执行 rm -rf build

+ export LANG=C
sudo make all LOG=debug  2>&1 | tee make_mac_x64.log

<pre>
----- Build times -------
Start 2020-04-11 18:16:40
End   2020-04-11 18:38:18

</pre>

<pre>
./build/macosx-x86_64-normal-server-fastdebug/jdk/bin/java -version
openjdk version "9-internal"
OpenJDK Runtime Environment (fastdebug build 9-internal+0-adhoc.root.jdk9)
OpenJDK 64-Bit Server VM (fastdebug build 9-internal+0-adhoc.root.jdk9, mixed mode)
</pre>

+ 导入idea ，hotspot目录
	- 按 docs/mac下编译openjdk1.9及集成clion动态调试 - 简书.pdf操作
	- hotspot (C++ 代码)
	
