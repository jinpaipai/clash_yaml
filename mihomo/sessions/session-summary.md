# Session 记录：clash_yaml 规则修改

**日期：** 2026-11-17
**目标仓库：** jinpaipai/clash_yaml（main 分支）

---

## 完成事项

### 1. Flightsimulator.list 扩展
- 原内容：4 条规则（virtualearth、flightsimulator keyword、kittyhawk akamaized、playfab content）
- 新增内容：AKAI Sunrise CDN、Azure Edge khstorelive/khmarketcdn、msgamestudios 服务集群、PlayFab UGC catalog
- 当前行数：21 条

### 2. gamedownload.list 扩展
- 原内容：84 行，覆盖 Epic/Ubisoft/Steam/Xbox/R星/EA/MC/战网/GOG/雷电/三角洲/网易/米哈游/Gal
- 新增平台及补充：
  - **Epic**：download[1-4]、Akamai分发、Unreal引擎CDN、Cloudflare镜像
  - **Blizzard**：blzddist 1-4（Akamai）、level3 CDN、各区域cdn、韩国cloudn、网易国服6个产品节点
  - **Xbox/微软商店**：assets1-2、xvcf传输、Microsoft Store下载链、大陆版assets
  - **Riot Games**：LoL/Lexington/Valorant/Wild Rift/Mock/Ares/Bacon等完整下载链
  - **GOG**：Akamai、Fastly、Cyberpunk专项
  - **Bethesda**：content + download cdp（辐射/上古卷轴/Doom）
  - **Rockstar**：gamedownloads akamaized.net
  - **EA**：Cloudflare镜像
  - **Ubisoft**：海外全版本 + 腾讯中国CDN
  - **Steam**：白山云trts、阿里云steampipe
  - **Nintendo Switch**：eShop补丁/游戏CDN、国行域名
- 最终行数：136 条

### 3. 工具环境搭建
- git credential store 配置完成（token 存于 ~/.git-credentials）
- gh CLI 安装至 `/c/Program Files/GitHub CLI/gh.exe`，已认证为 jinpaipai
- 工作目录锚定：`D:\文档\hermes_jinpai_project\github`

---

## 关键操作路径
- git 工作目录：`D:\文档\hermes_jinpai_project\github`
- 远端：https://github.com/jinpaipai/clash_yaml.git
- 每次使用 gh 前需在终端执行：
  ```bash
  export PATH="$PATH:/c/Program Files/GitHub CLI"
  export GH_TOKEN="<your-token>"
  ```

---

## 未完成任务 / 待办
- [ ] 确认 gamedownload.list 中是否有误加的 Steam 社区相关规则（目前仅含下载CDN）
- [ ] 考虑是否加入 Nintendo Switch Online 联机规则（与下载不同）
