# wakeword-ja-notebooks

[livekit-wakeword](https://github.com/livekit/livekit-wakeword) を使って日本語ウェイクワードモデルを学習するためのノートブック集です。

livekit-wakeword 本体のフォークは不要で、このリポジトリのノートブックを Kaggle または Google Colab で開くだけで使えます。

## ノートブック

| ファイル | 環境 | ウェイクワード |
|---|---|---|
| [notebooks/sensei_ja_kaggle.ipynb](notebooks/sensei_ja_kaggle.ipynb) | Kaggle | 先生 |
| [notebooks/sensei_ja_colab.ipynb](notebooks/sensei_ja_colab.ipynb) | Google Colab | 先生 |

## 使い方

### Kaggle（推奨）

1. [Kaggle](https://www.kaggle.com) にログインし、`notebooks/sensei_ja_kaggle.ipynb` をアップロード
2. 右パネル「Session options」→「Accelerator」→ **GPU T4 x2** を選択
3. 右パネル「Settings」→「Internet」を **ON** に設定
4. 上から順にセルを実行

> セッションが切れても、Kaggle Dataset にチャンクごと自動バックアップされるので途中から再開できます。

### Google Colab

1. `notebooks/sensei_ja_colab.ipynb` を Google Drive にアップロードして Colab で開く
2. ランタイム → ランタイムのタイプを変更 → **T4 GPU** を選択
3. 上から順にセルを実行

## 別のウェイクワードで使う場合

ノートブック内の設定セル（`CONFIG` を書き込むセル）を編集してください。

```yaml
target_phrases:
  - "your_phrase"       # カタカナ・ひらがな・漢字 どれでも可

custom_negative_phrases:
  - "音声的に近いフレーズ1"
  - "音声的に近いフレーズ2"
```

`custom_negative_phrases` には発音が似ている単語を手動で列挙してください（CMU Dict は英語専用のため、日本語の自動生成はできません）。

## 依存関係

livekit-wakeword 本体がノートブック内で自動インストールされます。手動インストールは不要です。

- [livekit/livekit-wakeword](https://github.com/livekit/livekit-wakeword)
- VoxCPM2（学習時に自動ダウンロード）
- espeak-ng（ノートブック内で自動インストール）
