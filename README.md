# Unity MMO Game

## 服务端

1. 安装SpacetimeDB

```
curl -sSf https://install.spacetimedb.com | sh
```

2. 安装Dotnet

```
wget https://builds.dotnet.microsoft.com/dotnet/Sdk/8.0.423/dotnet-sdk-8.0.423-linux-x64.tar.gz
mkdir -p $HOME/dotnet && tar zxf dotnet-sdk-8.0.423-linux-x64.tar.gz -C $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$DOTNET_ROOT
```

3. 启动SpacetimeDB服务

```
spacetime start
```

其他命令：

```
# 新建项目
spacetime init --lang=csharp server-csharp
# 初次同步服务端代码
spacetime publish --server local blackholio
# 更新服务端代码
spacetime publish --server local blackholio --delete-data
# 调用SayHello函数
spacetime call --server local blackholio say_hello
# 查看日志
spacetime logs --server local blackholio
# 生成unity客户端代码
spacetime generate --lang csharp --out-dir ../client-unity/Assets/autogen
# 登录和退出
spacetime login
spacetime logout
```

## 客户端

使用【Windows】->【Package Manager】->【Install package from git URL】安装下面插件：

```
https://github.com/clockworklabs/com.clockworklabs.spacetimedbsdk.git
```

原项目地址：https://github.com/beaucarnes/blackholio