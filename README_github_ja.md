# AI TRPG OS

GMが全情報を管理するのではなく、**PCの座標 × NPCの座標から見えるものだけをAIに生成させる**——それがAI TRPG OSの設計思想です。

各キャラクターは自分の座標からしか世界を見られない。その制約が、AIが情報を漏洩する誘惑を構造的に排除します。

座標とは「見えるもの × 動き方 × 一線」の一行で表したキャラクターの視点です。この掛け算の組み合わせにより、同じ場面でも兵士・商人・子供がそれぞれ違う世界を見て、違う行動をとります。

ClaudeにJSONファイルを読み込ませることで、この設計に基づいたTRPGのゲームマスターが動きます。ルール裁定・NPC演技・判定処理・セッション記録まで全部Claudeがやります。プレイヤーはチャットに行動を入力するだけです。

## できること

- **NPC演技** — 各NPCに「座標（見えるもの × 動き方 × 一線）」を設定。Claudeはその座標から外れた発言・行動を自動的に除外します
- **断片と変容** — NPCとの会話や行動が「断片」として蓄積され、一線に触れると座標が変容します
- **ノイズログ** — セッション中のAIのミスを類型化して蓄積する免疫ファイル。ミスを手続きパッチで埋めるのではなく、構造で埋めます
- **セッション間の記憶** — PlayLog・Session_Start・CharacterSheetの3ファイルでセッション状態を保存。次回読み込めば前回の続きから再開できます
- **自作TRPGに対応** — 付属テンプレートに自分のルールとシナリオを書き込むだけでどんなシステムでも動きます

## ファイル構成

```
AI_TRPG_OS_Core_v1_34_EN.json    # OS本体
NoiseLog_AI_TRPG_OS_v2_7_EN.json # AIのミスパターンを蓄積した免疫ファイル
StartPrompt_v1_25.json           # 初回セッション用
App_Template.json                # ルールシステムのテンプレート
Scenario_Template.json           # シナリオのテンプレート
```

## 使い方

### 1. プロジェクトを作る

claude.ai のプロジェクト機能に以下をアップロードします。

- `AI_TRPG_OS_Core_v1_34_EN.json`
- `NoiseLog_AI_TRPG_OS_v2_7_EN.json`
- 自分のAppファイル
- 自分のScenarioファイル

### 2. 初回セッション

新規チャットに `StartPrompt_v1_25.json` をアップロードして送ります：

```
全ファイルを読み込んで、StartPromptに従ってキャラクター作成を開始してください。
```

### 3. 2回目以降

前回のセーブファイル3点（Session_Start・PlayLog・CharacterSheet）をアップロードして送ります：

```
全ファイルを読み込んでセッションを再開してください。
```

## 自作TRPGを動かす

`App_Template.json` と `Scenario_Template.json` に自分のルールとシナリオを書き込むだけです。

既存システム（CoC7など）を使いたい場合は、公式PDFをClaudeに渡して変換させる手順をREADMEに記載しています。

## 動作環境

- [claude.ai](https://claude.ai)（Proプラン推奨）
- 他のチャットAI（Gemini、ChatGPTなど）でも動作しますが、安定性はClaudeが最も高いです

## 開発経緯

「TRPGがやりたい」と言ったら2ヶ月後にOSができていた話はこちら：
- [その1](https://note.com/rosy_swift4587/n/naaf56e8feaa5)
- [その2](https://note.com/rosy_swift4587/n/n9a3ae262bcd9)

実際に3セッション遊んだダウンロードページはこちら：
- [AI TRPG OS ダウンロード](https://note.com/rosy_swift4587/n/n4410b2b5d7f9)

## ライセンス

MIT License

付属のサンプルシナリオ・AppファイルにChaosium Inc. / KADOKAWAの著作物を含む場合は個人利用に限ります。
