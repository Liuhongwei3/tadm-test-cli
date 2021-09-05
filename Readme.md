# 发包

## tadm-test
```shell-script
mkdir tadm-test
cd tadm-test
npm init -y
# 编写入口文件，更新包信息、版本等
```

## npmjs.com
```shell-script
npm login
# username & password
cd tadm-test
npm publish

# 登录 npmjs.com 查看用户下的 packages 即可看到 tadm-test
# 到此成功发包到 npm
```

## Usage
```shell-script
npm i -g tadm-test
# 将会把 tadm-test 安装到 node 全局目录下，并可以在全局使用

# 可以使用以下命令找到
where tadm-test
# 进入对应文件夹的 node_modules 即可，当然你也可以先看看 tadm-test 和 tadm-test.cmd 里面写了什么
# 现在我们就可以在全局使用 tadm-test 命令
C:\Users\28731>tadm-test
tadm test
```

# npm link <package-name>

## Desc
	- `npm link`: 将当前项目链接到 node 全局 node_modules 中作为一个库文件，并解析 package.json 中的 bin 配置创建可执行文件，这样我们就可以在全局使用它
	- `npm link lib-name`: 将当前项目 node_modules 中指定的库文件链接到 node 全局 node_modules 下面对应的库文件，这样就可以将全局的库文件引用到项目中，不管他是从 npm 远程下载的还是本地作为调试我们自己的库(大多数是该场景)

## Example
```shell-script
cd tadm-test-lib
npm link

cd tadm-test
npm link tadm-test-lib
```

## Desc

# npm unlink <package-name>
	- `npm unlink`: 将当前项目从 node 全局 node_modules 中移除掉，这样我们就在全局不再找到它
	- `npm unlink lib-name`: 将当前项目中的库文件依赖移除，因为如果我们上一步如果已经在全局中移除了库文件，那么该引用就不再能够找到库文件，因此需要移除，换用安装远程 npm 包

## Example
```shell-script
cd tadm-test-lib
npm unlink

cd tadm-test
npm unlink tadm-test-lib

# maybe tadm-test-lib 不存在
rm rf node_modules
npm i
```
