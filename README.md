# TVBox 聚合影视源（每日自动测速更新）

基于 GitHub Actions 每日定时运行，自动聚合最新 TVBox / FongMi 影视源，全自动测速清洗、去重与智能分类。

本仓库已**彻底拆分成人源（pron / 18+ / 麻豆 / 福利等）与常规纯净源**，分为“家庭纯净版”与“成人专区版”，满足不同使用场景需求。

---

## 🚀 订阅源地址汇总

> **提示**：国内设备直接访问 GitHub Raw 可能会超时，建议优先使用下方提供的 **加速直链 (CDN)**。

### 🟢 1. 常规纯净版（推荐家庭/日常使用，已彻底剥离成人内容）

严格过滤所有 18+、成人、福利、麻豆、情色采集站及直播，适合全家老少共同使用：

| 版本 | 说明 | GitHub 原链 | 加速直链 (CDN) |
| :--- | :--- | :--- | :--- |
| **简洁纯净版** | 固定前 10 个最快且稳定的非成人采集站，真实测速排序，极速秒播 | [tvbox.json](https://raw.githubusercontent.com/lublue147-netizen/tvyuan/master/tvbox.json) | `https://gh-proxy.org/raw.githubusercontent.com/lublue147-netizen/tvyuan/master/tvbox.json` |
| **全量纯净版** | 包含 1200+ 站点与 110+ 央视/卫视常规直播源，带最新 spider 解析 | [tvbox_full.json](https://raw.githubusercontent.com/lublue147-netizen/tvyuan/master/tvbox_full.json) | `https://gh-proxy.org/raw.githubusercontent.com/lublue147-netizen/tvyuan/master/tvbox_full.json` |
| **多仓纯净版** | 90 个优质独立多仓，已过滤所有包含成人的仓库 | [tvbox_multi.json](https://raw.githubusercontent.com/lublue147-netizen/tvyuan/master/tvbox_multi.json) | `https://gh-proxy.org/raw.githubusercontent.com/lublue147-netizen/tvyuan/master/tvbox_multi.json` |

---

### 🔞 2. 成人专区版（包含成人直播、成人采集站与成人多仓）

专为个人及成年人打造，聚合 69 个成人/福利影视站与 12 个成人直播专线（含 pron、Sex、麻豆、18+ 直播等）：

| 版本 | 说明 | GitHub 原链 | 加速直链 (CDN) |
| :--- | :--- | :--- | :--- |
| **成人专线版** | 成人专属订阅！包含全部成人采集站 + 12 个成人直播 + 解密解析接口 | [tvbox_adult.json](https://raw.githubusercontent.com/lublue147-netizen/tvyuan/master/tvbox_adult.json) | `https://gh-proxy.org/raw.githubusercontent.com/lublue147-netizen/tvyuan/master/tvbox_adult.json` |
| **全量含成人版** | 完整未删减全量版：包含所有 1300+ 站点及所有 123 个直播源 | [tvbox_full_adult.json](https://raw.githubusercontent.com/lublue147-netizen/tvyuan/master/tvbox_full_adult.json) | `https://gh-proxy.org/raw.githubusercontent.com/lublue147-netizen/tvyuan/master/tvbox_full_adult.json` |
| **多仓含成人版** | 完整多仓：包含全部 93 个独立仓库（包含 3 个成人专用仓库） | [tvbox_multi_adult.json](https://raw.githubusercontent.com/lublue147-netizen/tvyuan/master/tvbox_multi_adult.json) | `https://gh-proxy.org/raw.githubusercontent.com/lublue147-netizen/tvyuan/master/tvbox_multi_adult.json` |

---

## 📺 客户端使用指南

### FongMi（丰米） / TVBox
1. 打开客户端，进入 **设置** → **配置**（或 **点播源** / **直播源**）。
2. 在地址输入框中，粘贴上方对应版本的 **加速直链**。
3. 点击确定，等待配置加载完毕即可正常观影。

### 多仓配置方式
- **FongMi（丰米）**：设置 → 配置 → 存储仓 / 多仓 → 粘贴 `tvbox_multi.json`（或 `tvbox_multi_adult.json`）。
- **影视仓**：首页 → 配置 → 多仓地址 → 粘贴对应多仓链接。

---

## ⚙️ 更新机制与技术特性

1. **每日定时自动刷新**：
   - GitHub Actions 每天 UTC 20:00（北京时间 04:00）自动触发更新。
   - 自动拉取上游源、进行节点测速与切片播放测试，自动清洗不可用站点并推送到本仓库。
2. **真实播放测速排序**：
   - 通过 `m3u8` 下载与分片 `ts` 实测，根据真实播放下载速度与首帧响应时间进行排序。
   - 优质高速站置顶（如索尼、360、光速等），确保点开即播。
3. **精准成人内容识别模型**：
   - 结合多重正则特征、关键字库与敏感域名/路径扫描，精确分类 69 个成人采集站与 12 个成人直播源。
   - 纯净版与成人版完全物理隔离，纯净版零泄露，老人与儿童可安心使用。
