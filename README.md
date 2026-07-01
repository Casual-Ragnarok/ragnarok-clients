---
license: apache-2.0
---

# Ragnarok Clients

Ragnarok Online 客户端资源索引，按年份、地区和语言整理 2010 年之后，也就是复兴（Renewal / RE）之后可用的客户端资源、补丁状态和下载来源。

## 目录

| 年份 | 地区 / 语言 | 说明 |
| --- | --- | --- |
| 2010 | [kRO](2010/kro.md) | 20101117 完整韩版客户端 |
| 2015 | [kRO](2015/kro.md) | 20150101 完整韩版客户端 |
| 2021 | [kRO](2021/kro.md) | 20210607、20211117 完整韩版客户端（共 3 个资源） |
| 2021 | [简中](2021/chs.md) | 20211103 随缘仙境简中客户端 |
| 2021 | [繁中](2021/cht.md) | 20211103 随缘仙境繁中客户端 |
| 2022 | [kRO](2022/kro.md) | 20220706 完整韩版客户端 |
| 2023 | [kRO](2023/kro.md) | 20230404 完整韩版客户端 |
| 2023 | [简中](2023/chs.md) | 20230404 随缘仙境简中客户端 |
| 2025 | [英文](2025/en.md) | 20250416 完整英文客户端 |
| 2025 | [kRO](2025/kro.md) | 20251204 完整韩版客户端 |
| 2026 | [kRO](2026/kro.md) | 20260519 韩版客户端（缺 Ragexe，内附 20260603 data.grf） |

## PRE 与 RE

这个仓库目前收集到的都是 2010 年之后的复兴后客户端。按照 [Ragnarok EP 版本时间线](https://exp-blog.com/game/ro/ragnarok-episode-timeline/) 的记录，EP13.2 `Encounter` 是 2008-12-17，`Renewal Release（3-1 Jobs）` 是 2009-06-17，复兴后的 EP13.3 `El Dicastes` 是 2009-12-23。

真正复兴前的 PRE 客户端，尤其是 2008 年前后、EP13.2 之前或附近的客户端，现在已经很难找到了。即使在 rAthena 中把 `renewal.h` 的 `#define PRERE` 取消注释，现有 Ragexe 或 RagexeRE 的封包也不一定能直接接入服务端。

因此，如果想要复兴前的体验，更现实的做法不是寻找完整 PRE 客户端，而是使用复兴后的 RE 客户端，并在服务端侧限制 RE 内容，间接得到接近 PRE 的端。

常见处理方式包括：注释掉职业变更脚本以移除第三职业；用源文件实现 `renewal.h` 中需要的功能，或者保留 `renewal.h` 但移除不需要的 Renewal 经验和掉落率限制。这样得到的是接近 PRE 的服务器环境，非第三职业仍然沿用 PRE 的计算方式。

二转前的职业伤害公式在 RE 和 PRE 中基本一致。

## 备注

Ragexe 与 RagexeRE 的区别：

```text
Ragexe   - kRO 正式服客户端 EXE
RagexeRE - kRO 测试服客户端 EXE
```

> 不少同学误以为 Ragexe 是复兴前、RagexeRE 是复兴后，这是不对的

## 参考

- [Ragnarok EP 版本时间线](https://exp-blog.com/game/ro/ragnarok-episode-timeline/)
- [Nemo](http://nemo.herc.ws/downloads/)

## 维护约定

每个年份目录下按地区维护 Markdown 文件：

- `kro.md`：韩版客户端
- `en.md`：英文客户端
- `chs.md`：简中客户端或简中补丁整合包
- `cht.md`：繁中客户端或繁中补丁整合包

新增条目时建议包含客户端名称、日期、是否改动、补丁状态、下载地址和获取命令。

## GitHub Pages

静态页面由 `scripts/generate_pages.py` 根据各年份目录中的 Markdown 文件自动生成：

```bash
python scripts/generate_pages.py
```

生成结果位于 `docs/index.html`。推送到 `main` 分支后，GitHub Actions 会重新生成并部署页面。仓库首次启用时，需要在 GitHub 的 **Settings → Pages → Build and deployment → Source** 中选择 **GitHub Actions**。
