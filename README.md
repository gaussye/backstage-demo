# [Backstage](https://backstage.io)

## 前置条件
1.参考文档 https://backstage.io/docs/getting-started/ 确保开发工具和环境已经配置好。

2.创建github token以备后面的step2使用，参考文档

3.创建github Auth APP client id和client secret 参考文档 (https://backstage.io/docs/auth/github/provider#create-an-oauth-app-on-github)


## 运行backstage
这是一个通过backstage创建EKScomponent的例子，需要运行, 请执行以下命令：

step 1 - 安装依赖:
```sh
yarn install
```

setp 2 - 导入环境变量（注意github token以及client id，secret需要替换成你自己的）:
```sh
export GITHUB_TOKEN=ghp_xxx
export NODE_OPTIONS=--no-node-snapshot
export AUTH_GITHUB_CLIENT_ID=12e14xxxx
export AUTH_GITHUB_CLIENT_SECRET=13cfxxxx
```
set 3 - 运行backstage
```sh
yarn dev
```
## 注意事项
1.如果使用ssh远端开发功能，记得在VS code检查frontend和backend的端口是否做了转发，不然会访问不了。

2.模板放在根目录的templates下面，通过app-config配置，可以自行修改。模板的步骤可以自己定定义。模板的step注释了github-action步骤，如果需要通过github action执行部署操作可以开启（action代码可以参考gaussye/my-test-github-action）。

3.模板也可以放在github，需要修改app-config,注意type类型
```sh
    - type: url
      target: https://github******
```

4.如果要开启debug模式，执行 'LOG_LEVEL=debug yarn dev'


5.使用k8s plugin应用需要打label不然无法识别。










