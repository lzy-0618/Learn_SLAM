## 1. 配置git，g++,cmake，eigen，Sophus

```
# 安装git
yum install git 
```

```
# 安装g++
yum install gcc gcc-c++
```

```
# 安装 cmake

yum install -y wget
// 下载源代码压缩包
wget https://cmake.org/files/v3.10/cmake-3.10.0-rc3.tar.gz
// 解压
tar -zxvf cmake-3.10.0-rc3.tar.gz

cd cmake-3.10.0-rc3/
./bootstrap
gmake
gmake install
```

```
# 安装 eigen库
wget https://gitlab.com/libeigen/eigen/-/archive/3.3.9/eigen-3.3.9.tar.gz
tar -zxvf eigen-3.3.9.tar.gz
cd eigen-3.3.9 # 进入eigen解压的目录
mkdir build  # 新建一个build文件夹
cd build  # 进入build文件夹
cmake ..  # 用cmake生成Makefile
make install  # 安装

// 设置软连接
ln -s /usr/local/include/eigen3/Eigen /usr/local/include/Eigen
ln -s /usr/local/include/eigen3/unsupported /usr/local/include/unsupported 
```

```
# centos 安装 Pangolin 失败
yum install freeglut
yum install libGLEW

#
cd /etc/yum.repos.d/
vi linuxtech.repo
// 复制下面内容 然后:wq 退出
[linuxtech]
name=LinuxTECH
baseurl=http://pkgrepo.linuxtech.net/el6/release/
enabled=1
gpgcheck=1
gpgkey=http://pkgrepo.linuxtech.net/el6/release/RPM-GPG-KEY-LinuxTECH.NET


# 然后回到 cd/home/用户名
yum install libglew-devel

yum install boost

// 乌班图应该可以 搜到安装教程
```

```
# 安装 Sophus

// 先按照fmt
git clone  https://github.com/fmtlib/fmt.git
cd fmt
mkdir build
cd build
cmake ..
make
sudo make install

// 安装sophus
git clone https://github.com/strasdat/Sophus.git
cd Sophus/

mkdir build
cd build
cmake ..
make
sudo make install
```
