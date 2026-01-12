---
theme: seriph
background: https://images.unsplash.com/photo-1550751827-4bd374c3f58b?auto=format&fit=crop&q=80&w=2070
class: text-center
highlighter: shiki
drawings:
  persist: false
transition: slide-left
title: Web Application A&D Exercise
author: Keitaro Yamazaki
---

# WebアプリケーションA&D演習
セキュリティ・キャンプ2026ミニ（大阪開催）

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer hover:bg-white/10" title="Next Page">
    Press Space for next page <carbon:arrow-right class="inline"/>
  </span>
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

## 山崎 啓太郎 (Keitaro Yamazaki)

- 京都大学情報学研究科修了
- 大手ユーザ企業のプロダクトセキュリティ業務
- 現在はセキュリティ企業にてWebペネトレーションテストやソースコード診断に従事
- CTF実績: DEF CON CTF, Google CTF Finals 複数回出場, SECCON CTF 13 Finals 優勝等
- 講師歴: セキュリティ・キャンプ全国大会 2022・2023 講師
- 著書: 「実践 Webペネトレーションテスト」
  <br>
  <img src="https://images-na.ssl-images-amazon.com/images/P/4814401256.09.LZZZZZZZ.jpg" class="h-40 shadow-lg rounded" alt="Practical Web Penetration Test Cover"/>

---

# 講義の背景

### Webアプリケーションの脆弱性

- 毎日多くの脆弱性が発見されている
- 単純なミスから、設計・運用に関わる複雑なものまで
- 限られた時間での優先順位判断が求められる

> [!IMPORTANT]
> 実際の運用では「直しやすさ」だけでなく「ビジネスへの影響」や「対応の限界」を考慮する必要があります。

---

# Attack & Defense (A&D) とは？

攻撃と防御の同時並行

<div class="grid grid-cols-2 gap-4 mt-4">
  <div class="p-4 border rounded border-red-500/50 bg-red-500/10">
    <h3 class="text-red-400">Attack (攻撃者視点)</h3>
    <ul class="text-sm">
      <li>脆弱性の発見と悪用</li>
      <li>フラグの取得</li>
      <li>相手の防御・監視を意識した攻撃</li>
    </ul>
  </div>
  <div class="p-4 border rounded border-green-500/50 bg-green-500/10">
    <h3 class="text-green-400">Defense (防御者視点)</h3>
    <ul class="text-sm">
      <li>脆弱性の修正（パッチ）</li>
      <li>サービスの機能維持 (SLA)</li>
      <li>攻撃の検知と解析 (ログ・パケット)</li>
    </ul>
  </div>
</div>

---

# 講義の狙い

二つの視点を行き来することで、セキュリティをより深く理解する

- **攻撃者の立場**:
  - どう悪用できるか？
  - どうすれば検知を逃れられるか？
- **防御者の立場**:
  - どう直すのが最適か？（機能への影響は？）
  - 攻撃の痕跡はどこに残るか？

---
layout: center
class: text-center
---

# 演習スタート！

A&D形式の面白さを体験しましょう。
質問があればいつでもどうぞ。
