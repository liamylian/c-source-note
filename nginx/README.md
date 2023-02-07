# NGINX 源码笔记

## 一、Ubuntu CLion 调试环境配置

### 1.1 安装 nginx 依赖

```shell
sudo apt install libpcre3 libpcre3-dev zlib1g zlib1g-dev
```

### 1.2 下载 Nginx 源码

```shell
git clone git@github.com:nginx/nginx.git
```

### 1.3 生成 CMakeLists.txt 文件，给 CLion 项目使用

```shell
cd nginx
# 拷贝 cmake 文件
cp ../c-souce-note/nginx/cmake auto/
# 在 auto/configure 文件中的 ". auto/make" 行之前，增加一行 ". auto/cmake"
sed -i '/\. auto\/make/i\\. auto\/cmake' auto/configure
# 生成 CmakeLists.txt 等文件
./auto/configure --prefix=`pwd` --with-debug
# 将 CmakeLists.txt 文件拷贝至项目根目录
cp objs/CmakeLists.txt .
```

### 1.4 使用 CLion 打开 nginx 源码目录

## 参考

- [Nginx-Cmake](https://github.com/Toudsour/nginx_cmake)