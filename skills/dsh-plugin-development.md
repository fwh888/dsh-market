# DSH 插件开发指南

## 插件形态（Cordis）
插件是 ESM 模块：

```js
export const name = "my-plugin";
export const inject = ["tools"];
export const apply = (ctx, config) => { /* ctx.tools.register ... */ };
```

## 配置（schemastery）
`export const Config = z.object({...})`，自动生成设置 UI。

## 打包 bundle
package.json 声明 `dsh.bundle.patch`；`dsh plugin --profile web add <pkg>` 安装。

## 关键缝
ctx.llm / ctx.tools / ctx.web / ctx.skills / ctx.shell / ctx.fs / ctx.sandbox / ctx.credentials / ctx.webServer。

## 规范
工具 snake_case；技能名 kebab-case；可选参数省略 required；密钥走 credential-ref。