# juzhi-updates

多项目应用更新包仓库（**公开**，供 app 内自动更新匿名拉取，无需令牌）。

## 目录结构

`
<项目名>/
  version.txt         # 纯文本版本号，如 1.0.4
  <资产>.apk           # 最新安装包（固定文件名，覆盖更新）
`

- TV 端：juzhi_flutter_tv/（juzhi_tv_armv7.apk / juzhi_tv_arm64.apk）
- APP 端：juzhi_flutter/（待接入）

## 客户端拉取约定

- 版本检查：https://raw.githubusercontent.com/fushengcf/juzhi-updates/main/<项目>/version.txt
- 安装包：.../main/<项目>/<资产>.apk（按设备 ABI 选 armv7 / arm64）
- 走国内加速镜像（ghproxy 系）对 raw 链接同样有效。

## 发布

在 juzhi_flutter_tv / juzhi_flutter 仓库根执行 	ool/publish_update.ps1（ForgeCI 构建完成后跑），
或手动：把新 apk 覆盖进对应目录、更新 version.txt、commit + push。
