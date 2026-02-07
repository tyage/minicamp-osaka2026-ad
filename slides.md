---
theme: seriph
class: text-center
highlighter: shiki
drawings:
  persist: false
transition: slide-left
title: Web Application A&D Exercise
author: Keitaro Yamazaki
---

# Web Application Attack & Defense

<div class="text-2xl font-bold opacity-80">
  Attack & Defense形式のCTFでリアルタイムの攻防戦を体験してみよう
</div>

<div class="mt-4 text-sm opacity-60">
  セキュリティ・キャンプ2026ミニ（大阪開催）
</div>

<div class="abs-br m-6 flex gap-2">
  <a href="https://github.com/tyage/minicamp-osaka2026-ad" target="_blank" alt="GitHub" title="Open in GitHub"
    class="text-xl icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>

---
layout: intro
---

# 自己紹介

<div class="grid grid-cols-[1fr_200px] gap-8 items-start mt-8">

<div>

## 山崎 啓太郎 (@tyage)

<div class="opacity-90 text-base leading-relaxed">

- **経歴**
  - 2010年 セキュリティ&プログラミングキャンプ卒業
  - 2018年～ LINE株式会社 アプリケーションセキュリティチーム
  - 2020年～ GMOサイバーセキュリティ byイエラエ株式会社 高度診断部
- **CTF**
  - **Player**: DEF CON CTF, Google CTF Finals 出場, SECCON CTF 13 Finals 優勝等
  - **Organizer**: ICC Tokyo 2025, CODE BLUE CTF等
- **講師歴**
  - セキュリティ・キャンプ全国大会 2022・2023 講師
- **著書**
  - 「実践 Webペネトレーションテスト」

</div>
</div>

<div class="flex flex-col items-center gap-2">
  <img src="https://images-na.ssl-images-amazon.com/images/P/4814401256.09.LZZZZZZZ.jpg" class="shadow-xl rounded-lg border border-gray-200 w-full" alt="Book Cover"/>
</div>

</div>

---
layout: center
class: text-center
---

# Q. CTFに参加したことある人✋️

---
layout: center
class: text-center
---

# Q. A&D形式のCTFに参加したことある人✋️

---

# CTF (Capture The Flag) とは？

情報セキュリティ技術を競う競技

- **目的**: 隠された「Flag（旗）」を見つけ出すこと
- **主な形式**:
  - **Jeopardy（ジョパディ）形式**:
    - Web, Crypto, Pwn, Reversing... などカテゴリ別の問題を解く
    - 最も一般的
  - **Attack & Defense (A&D) 形式**:
    - チームごとに守るべきサーバー/サービスがある
    - 自チームを守りつつ、他チームを攻撃する
    - **<span class="text-orange-400">今回の演習はこの形式！</span>**

---

# ICC (International Cybersecurity Challenge) とは？

<div class="grid grid-cols-[1.3fr_1fr] gap-8 mt-8 items-center">

<div>

### 25歳以下の若手実力者が集う世界大会

各地域（欧州、アジア、米国など）の予選を勝ち抜いた代表チームによる対抗戦。

<div class="mt-8 p-4 bg-gray-50 dark:bg-gray-800/50 rounded-lg border border-gray-200 dark:border-gray-700">

<div class="font-bold mb-2 flex items-center gap-2 text-lg">
  <span>🇯🇵</span>
  <span>2025年、その世界大会が日本に上陸</span>
</div>

**ICC Tokyo** として、内閣サイバーセキュリティセンター (NISC) 主催のもと幕張で開催されました。

- **競技形式**: <span class="text-blue-500 font-bold">Jeopardy</span> と <span class="text-red-500 font-bold">Attack & Defense</span> の2種目
- **参加**: アジア・オセアニアを含む世界8地域の選抜チーム

</div>

</div>

<div class="grid grid-cols-2 gap-2 h-full">
  <div class="bg-gray-200 dark:bg-gray-700 rounded-lg aspect-video flex items-center justify-center text-xs text-gray-500">Competition Area</div>
  <div class="bg-gray-200 dark:bg-gray-700 rounded-lg aspect-video flex items-center justify-center text-xs text-gray-500">Team Asia</div>
  <div class="bg-gray-200 dark:bg-gray-700 rounded-lg aspect-video flex items-center justify-center text-xs text-gray-500">Ceremony</div>
  <div class="bg-gray-200 dark:bg-gray-700 rounded-lg aspect-video flex items-center justify-center text-xs text-gray-500">Networking</div>
</div>

</div>

---

# ICCにおける Attack & Defense

<div class="grid grid-cols-2 gap-12 mt-8 items-center">

<div>

### <span class="text-red-500">Attack</span> & <span class="text-blue-500">Defense</span>

- **全チームに同じ「脆弱な環境」が配布される**
- 自軍の穴を塞ぎつつ(Patch)、他チームを攻撃(Exploit)

<div class="mt-6">

### オペレーションの極限

- **「パッチを当てたらサービスが止まった」**
  - 可用性(Availability)チェックが通らず減点
- **「防御に時間をかけすぎて攻撃の手が回らない」**
  - 攻防のリソース配分と意思決定のスピード勝負

</div>

</div>

<div class="bg-gray-50 dark:bg-gray-800 p-8 rounded-xl border border-gray-100 dark:border-gray-700 flex items-center justify-center">
  <div class="text-center">
    <div class="text-5xl mb-4">⚖️</div>
    <h3 class="font-bold text-lg mb-2">SLA vs Security</h3>
    <p class="opacity-80">
      動かし続けなければならない。<br>
      しかし、守らなければならない。
    </p>
    <div class="mt-4 text-xs opacity-60">
      このジレンマこそが<br>A&Dの醍醐味であり本質
    </div>
  </div>
</div>

</div>

---

# 世界の代表的な A&D CTF

ICC以外にも、世界中でAttack & Defense形式のCTFが開催されています。

<div class="grid grid-cols-2 gap-8 mt-8">

<div class="bg-black/5 dark:bg-white/5 p-6 rounded-xl border border-gray-200 dark:border-gray-700">

### DEF CON CTF

- **世界最高峰**のハッキング大会
- ラスベガスで毎年開催される決勝戦は伝統的にA&D形式
- 独自アーキテクチャや未知の脆弱性が飛び交う

</div>

<div class="bg-black/5 dark:bg-white/5 p-6 rounded-xl border border-gray-200 dark:border-gray-700">

### HITCON CTF

- 台湾で開催されるハイレベルなCTF
- A&Dのクオリティが非常に高く、世界中のトップチームが参加
- Web, Pwn, Cryptoなどバランスの良い出題

</div>

</div>

---

# 攻撃者の視点 (Attacker)

脆弱性を見つけ、他チームを攻撃してFLAGを奪取する

- 配布されたソースコードを読み解く
- Fuzzingなどで実際にデータを送って挙動を確認
- Exploitを作成して他チームのサーバーに投下
- FLAGを取得してスコアサーバーに提出

---

# 防御者の視点 (Defender)

自軍のサーバーを守り、攻撃を検知して修正する

- 脆弱性を塞ぐ（サービスを壊さないように慎重に）
- パケットキャプチャやログを監視する
- 敵の攻撃パケットは「答え」でもある
- SLAを維持しながら、攻撃を分析して反撃の糸口を探る

---
layout: center
class: text-center
---

# 演習スタート！

## A&D環境に触ってみよう

スコアボードの確認、サーバーへのアクセス、<br>
まずは「何が動いているか」を確認してください。

<div class="mt-8 text-sm opacity-60">
  質問があればいつでもメンターに声をかけてください
</div>

---

# 高度な攻防 (1): 情報の非対称性

攻撃することは、脆弱性の場所を教えること

- 攻撃パケットは防御側のログに残る
- 上位チームの攻撃は、下位チームにとって「最高のお手本」となる
- 攻撃者は、他のチームに検知されないよう慎重に攻撃する必要がある
- 攻撃するほど、自分の手の内が相手に見える→「諸刃の剣」

---

# 高度な攻防 (2): 攻撃の再利用 (Replay Attack)

原理がわからなくても、攻撃はできる

- 来たパケットをそのまま投げ返す
- 脆弱性の詳細を知らなくても得点できてしまう
- 会場全体に同じ攻撃が蔓延する（Replay Storm）

---

# 高度な攻防 (3): 解析を拒む技術

攻撃を隠し、解析を遅らせる

- 通信を暗号化し、盗聴・ReplayされてもFLAGを守る
- 偽の攻撃を大量に混ぜ、どれが本命か分からなくする
- 終了間際まで攻撃を隠し持ち、パッチの時間を与えない

---

# 番外編: Player vs Organizer

> 「A&D は本質的に壊れていて、終わっている」

<div class="mt-4 text-xs opacity-60 break-all">
  Reference: https://github.com/hugeh0ge/substitute-of-blog/blob/main/blog/2026-01-01-how-to-create-ad-ctf-problems_ja.md
</div>

### 良い問題を作るのは難しい

- 理想：脆弱性を見つけ、修正し、攻撃する
- 現実：「反射神経ゲー」になりがち。修正が簡単すぎると差がつかない。難しすぎると誰も直せない。

### それでもA&Dをやる理由

- この「カオス」こそが現実のインシデント対応に近い
- 理不尽な状況下での意思決定、リスク管理
- 何より、燃える（楽しい）


