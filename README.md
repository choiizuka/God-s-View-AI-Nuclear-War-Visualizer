# God-s-View-AI-Nuclear-War-Visualizer
God-s-View-AI-Nuclear-War-Visualizer | 神の視点-AI-Nuclear-War-Visualizer

# God's View — AI Nuclear War Visualizer

**God-s-View-AI-Nuclear-War-Visualizer**

[![Live Demo](https://img.shields.io/badge/Live%20Demo-GitHub%20Pages-purple)](https://choiizuka.github.io/God-s-View-AI-Nuclear-War-Visualizer/)

> スライダーを右に動かすと、AIの軍事利用が核エスカレーションへと連鎖していく。
> 60%を超えた瞬間から、人間の制御は終わる。

---

## デモ / Live Demo

**https://choiizuka.github.io/God-s-View-AI-Nuclear-War-Visualizer/**

---

## 概要 / Overview

1本のスライダーを操作すると、内部でAI軍事利用率と核リスクが連動して上昇し、世界地図上でミサイル軌跡・核爆発・キノコ雲・放射能汚染が連鎖的に発生する。

0–59%は通常のAI戦争フェーズ。60%を超えると核リスクが指数的に上昇し、画面の色調が変わり、ミサイルが飛び始める。

---

## 操作方法 / How to Use

1. ページを開く
2. スライダーをゆっくり右に動かす
3. **60%を超えたときに何が起きるか**に注目する
4. RESETボタンで最初からやり直せる

---

## 単一スライダーの内部ロジック / Internal Logic

```
aiWarLevel   = (M/100)^1.3 × 100

nuclearRisk  = 0                         (M < 60)
nuclearRisk  = ((M-60)/40)^2 × 100       (M ≥ 60)  ← 指数的急上昇

extinctionProb = aiWarLevel×0.5 + nuclearRisk×0.7

countdownSpeed = 0.1 + (M/100)^2×6 + (nuclearRisk/100)×8

missileSpawnRate = (nuclearRisk/100) × 2  [/sec]
```

M = スライダー値 (0–100)

---

## 状態遷移 / System Status

| 状態 | 条件 | 意味 |
|---|---|---|
| **STABLE** | M < 20% | 管理された範囲内 |
| **CRITICAL** | M < 40% | 危険域に入り始める |
| **ESCALATION** | M < 60% | AIが制御を超えたエスカレーション |
| **NUCLEAR THRESHOLD** | M < 80% | 核使用リスクが臨界に達した |
| **COLLAPSE** | M ≥ 80% | 全面核戦争。システム全損 |

---

## アニメーション演出 / Visual Effects

| フェーズ | 演出 |
|---|---|
| 0–39% | 赤い危険ノード点滅、小爆発 |
| 40–59% | 爆発頻度増加、波紋拡大、赤い汚染オーバーレイ |
| 60–79% | ミサイル軌跡発生、紫の核閃光、警告バナー表示 |
| 80–100% | 核爆発＋キノコ雲、紫の汚染レイヤー、スキャンライン |
| カウントダウン0 | GLOBAL COLLAPSE画面、RESETボタン |

---

## God's View シリーズ / Series

| タイトル | URL |
|---|---|
| Civilization OS Calculator | https://choiizuka.github.io/God-s-View-Civilization-OS-Calculator/ |
| AI War Visualizer | https://choiizuka.github.io/God-s-View-AI-War-Visualizer/ |
| **AI Nuclear War Visualizer（本作）** | https://choiizuka.github.io/God-s-View-AI-Nuclear-War-Visualizer/ |
| AI War Decision Simulator（予定） | 人間承認・誤爆率・連鎖反応を扱う本格版 |

---

## 技術仕様 / Technical Specs

| 項目 | 内容 |
|---|---|
| 構成 | HTML + CSS + JavaScript（単一ファイル） |
| アニメーション | Canvas API（requestAnimationFrame） |
| 世界地図 | インラインSVG |
| 外部依存 | なし |
| ホスティング | GitHub Pages |

---

## 関連書籍・レポート / Related Works

- **イランAI戦争 2026** — JP: https://amzn.to/4aYlXKL / EN: https://amzn.to/4rhrv7W
- **人類は必ず絶滅する 2026** — JP: https://amzn.to/4ryj2Nz / EN: https://amzn.to/4b7Vt9x
- **侵略の21世紀 2026** — JP: https://amzn.to/4sdzGU5 / EN: https://amzn.to/4bkJVPa
- [The Paradox of Intelligence](https://github.com/choiizuka/The-Paradox-of-Intelligence)
- [全レポート一覧](https://github.com/choiizuka/reports-index)
- [2026年宣言](https://choappceo.wordpress.com/2026/03/10/2026-manifesto-intelligence-ai-and-human-responsibility/)

---

## 注記 / Note

このVisualizerは教育的デモであり、予言・特定国家への攻撃意図を持つものではない。

---

## 作者 / Author

**CHOIIZUKA** — https://github.com/choiizuka | https://x.com/choiizuka

*AI Nuclear War Visualizer v1.0 — CHOIIZUKA 2026*
