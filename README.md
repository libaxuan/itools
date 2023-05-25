# 开发人员和 IT 工作人员工作工具

这些工具可用于开发人员和从事 IT 工作的人员。请访问 [itools.tech](https://itools.tech) 查看。

## 功能和路线图

请查看 [issues](https://github.com/libaxuan/itools/issues)，看看是否有要实现的功能。

如果您有新工具的想法，请提交 [feature request](https://github.com/libaxuan/itools/issues/new?assignees=libaxuan&labels=&template=feature_request.md&title=)！

## 自主托管

在家庭实验室中自主托管解决方案

**从 Docker Hub：**

```sh
docker run -d --name itools --restart unless-stopped -p 8080:80 libaxuan/itools:latest
```

**从 GitHub Packages：**

```sh
docker run -d --name itools --restart unless-stopped -p 8080:80 ghcr.io/libaxuan/itools:latest
```

## 贡献

### 推荐的 IDE 设置

[VSCode](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar)（并禁用 Vetur）+ [TypeScript Vue Plugin (Volar)](https://marketplace.visualstudio.com/items?itemName=Vue.vscode-typescript-vue-plugin)。

### TypeScript 中的 `.vue` 导入类型支持

TypeScript 默认无法处理 `.vue` 导入的类型信息，因此我们使用 `vue-tsc` 替换 `tsc` CLI 进行类型检查。在编辑器中，我们需要 [TypeScript Vue Plugin (Volar)](https://marketplace.visualstudio.com/items?itemName=Vue.vscode-typescript-vue-plugin) 使 TypeScript 语言服务了解 `.vue` 类型。

如果独立的 TypeScript 插件对您来说不够快，请使用 Volar 实现的 [Take Over Mode](https://github.com/johnsoncodehk/volar/discussions/471#discussioncomment-1361669)。您可以按照以下步骤启用它：

1. 禁用内置的 TypeScript 扩展
   1. 运行 VSCode 命令面板中的 `Extensions: Show Built-in Extensions`
   2. 找到 `TypeScript and JavaScript Language Features`，右键单击并选择 `Disable (Workspace)`
2. 运行命令面板中的 `Developer: Reload Window` 重新加载 VSCode 窗口
