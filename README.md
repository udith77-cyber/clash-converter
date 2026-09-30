# 订阅转换 · 冰川极地

一个简洁美观的**订阅转换网页工具**：把机场 / 节点订阅链接，一键转换成 Clash、ShadowRocket、Surge、Sing-Box 等客户端可用的配置文件。

在线使用：https://udith77-cyber.github.io/clash-converter/

## 工作原理

本项目是一个**纯静态网页前端**（单个 `index.html`，无构建步骤），实际转换由兼容 [subconverter](https://github.com/tindy2013/subconverter) 协议的后端接口完成：

1. 你在页面上粘贴订阅链接、选择目标客户端和配置模板；
2. 页面按 subconverter 规范拼出一条转换请求 URL（默认后端 `api.v1.mk`）；
3. 后端拉取你的订阅、按模板生成配置文件并返回链接，你直接复制使用。

## 功能特性

- **多订阅合并**：输入框支持多行粘贴，多条订阅一次转换
- **多目标客户端**：Clash、ShadowRocket、Surge 4/5、Sing-Box、V2Ray、Trojan、ShadowsocksR、混合订阅（mixed）
- **配置模板**：内置 20+ ACL4SSR 规则模板（按 Online / Mini / Full / 去广告等分组），也支持填入自己的自定义配置 URL
- **高级选项**：节点名 Emoji、启用 UDP、TCP Fast Open、跳过证书验证、Clash DoH、XUDP、插入默认节点、输出节点列表、过滤非法节点等
- **转换历史**：最近的转换记录自动保存，可一键清空
- **纯前端、无需安装**：打开网页即用，也可本地双击打开

## 使用方法

1. 打开 [在线页面](https://udith77-cyber.github.io/clash-converter/)
2. 在「订阅链接」输入框粘贴你的订阅地址（支持多条，每行一条）
3. 选择「目标类型」（你用的客户端，如 Clash）
4. 选择「配置模板」：
   - 新手推荐 `ACL4SSR_Online_Mini`，规则精简、速度快
   - 想自己控制规则，可选 `ACL4SSR` 全量系列或填入自定义配置 URL
5. 按需在「高级选项」里微调参数（如节点名 Emoji、启用 UDP）
6. 点击「转换」，复制生成的订阅链接，粘贴到客户端即可使用

> 快捷键：`Ctrl / ⌘ + Enter` 可快速转换。

## 本地运行 / 自行部署

```bash
git clone <本仓库地址>
cd clash-converter
# 直接用浏览器打开 index.html 即可，无需构建
```

也可推送到自己的 GitHub 仓库，通过 **GitHub Pages** 一键发布（本项目已内置 `.github/workflows` 自动部署配置）。

## 更换转换后端

默认转换后端为 `https://api.v1.mk/sub`。如需更换，在 `index.html` 中搜索 `api.v1.mk` 并替换为你自己的 subconverter 服务地址即可。

## 隐私说明

- 你输入的订阅链接和转换历史**只保存在本机浏览器**（localStorage），不会上传到本站服务器（本站是静态页面，本身就没有服务器）。
- 但转换请求会经过你选择的后端接口（默认 `api.v1.mk`），订阅链接会发送到该后端以完成转换，请自行评估信任度；介意的话可以自建 subconverter 服务并按上节方法更换。

## 常见问题

**Q：转换后导入客户端没节点？**
A：先确认订阅链接本身有效（浏览器直接打开能看到内容），再检查是否勾选了「过滤非法节点」，部分失效节点会被剔除。

**Q：想用自己的分流规则？**
A：在配置模板下拉框选择「自定义配置 URL」，填入你的 ini 配置文件地址即可（格式参考 ACL4SSR 的 ini 文件）。

**Q：页面打不开 / 转换失败？**
A：检查网络是否能访问在线页面及转换后端；本地打开 `index.html` 时部分浏览器对 `file://` 协议有限制，建议用本地静态服务器或直接使用在线版。

## License

MIT
