# Verifier · 校验器

本目录定义本仓库的验收标准（V1–V6），并在 `runs/` 下留存每次全量校验的时间戳记录。

## 验收标准 / Acceptance Checks

- **V1 仓库公开 / Repository is public**：未登录状态下可访问仓库主页（HTTP 200）。
- **V2 中文五件与底稿一致 / Chinese five items match the masters**：`zh/01`、`zh/03`、`zh/04`、`zh/05` 与底稿逐字节一致（以 Git blob SHA 比对）；`zh/02-准则·文明资产审计报告/` 目录内六个分卷文件按文件名顺序拼接，等于《文明资产审计报告》全本底稿（53,060 字，含序 + 三十六章 + 终页），且每个分卷边界均落在章节开头。
- **V3 英文四件，无判例 / English set has four items, no Case**：`en/` 下恰为 01、02、04、05 四件；《局外人 / The Outsider》铁律不入英文版——`en/` 内任何文件不得出现「局外人」或「Outsider」。
- **V4 英文准则全本 / English Standard complete**：`en/02-The-Standard-The-Civilization-Asset-Audit-Report/` 拼接后含 38 个核心标题（Preface + Chapter 1–36 + Final Page），总词数不少于 25,000 英文词；任何英文文件内不得残留中文字符（署名「锋十二」除外）。
- **V5 README 双语合规 / README bilingual compliance**：中英双语；含电子版免费流通声明与发行规则（每一语种每十万使用人口限发一册纸质版）；署名只用 Feng 12（锋十二）；全仓库任何文件不得出现真名（真名只见于法律文件）。
- **V6 术语一致 / Terminology consistency**：核心术语中英对照在两侧全文中均出现且口径统一，如 贞节币 = the Chastity Coin、父权叙事银行 = the Patriarchal Narrative Bank、神权叙事银行 = the Theocratic Narrative Bank、回音壁 = the echo wall、跑步机 = treadmill、验钞机 = the counterfeit detector、兑付条款 = Redemption Clause、本质先于存在 = Essence precedes existence、观测即乞丐，证明即地狱 = To observe is to become a beggar; to prove is to enter hell 等。

## 方法 / Method

内容一致性以 Git blob SHA-1 比对（`sha1("blob {len}\0" + content)`）为准；计数类指标（字数、标题数）在本地底稿上统计，底稿与远端逐文件经 SHA 比对确认同源后，本地统计即视为远端统计。

## 运行记录 / Run Records

见 `runs/` 目录，每次全量校验一份带时间戳的记录文件。