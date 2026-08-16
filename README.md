# Harry的工作台（PWA）

年 / 月 / 周 / 日 四级目标拆解 + 完成率仪表盘，支持**手机安装**与**电脑/手机云同步**。

## 功能
- 年度 → 月 → 周 → 每日待办 四级拆解
- 完成率仪表盘（总完成率环、近 7 日趋势、各目标进度条）
- 逾期自动顺延 + 「今天要处理」置顶区
- 离线可用（Service Worker 缓存）
- 跨设备云同步（GitHub Gist，电脑与手机共用一份数据）

## 手机安装
1. 用支持 PWA 的浏览器（Android Chrome / Edge；iPhone 用 Safari）打开部署后的地址：
   `https://<你的用户名>.github.io/harry-workbench/`
2. 菜单 →「添加到主屏幕」（iPhone 为「分享 → 添加到主屏幕」）。
3. 桌面上会出现「Harry台」图标，点开即全屏 APP，可离线使用。

## 开启云同步（电脑/手机互通）
1. 生成一个 GitHub 个人令牌（classic），勾选 `gist` 权限：
   https://github.com/settings/tokens
2. 在 APP 内点右上角「云同步」→ 粘贴令牌 → 连接并同步。
3. 电脑和手机都用同一个令牌连接，数据自动双向同步（按时间戳后写覆盖，LWW）。
4. 令牌仅保存在你本机浏览器，不上传任何第三方。

## 本地预览（开发）
```
cd harry-workbench
python3 -m http.server 8137
# 浏览器打开 http://127.0.0.1:8137/
```

## 部署到 GitHub Pages
见 `deploy.ps1`（Windows PowerShell，需你的 GitHub Classic PAT，权限 `repo` + `gist`）。
