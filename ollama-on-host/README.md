# ホスト上で Ollama を起動している場合

## 事前準備

## Ollama

### インストール

Ollama をインストールする

https://ollama.com/

### 生成AIモデルのダウンロード

Ollama の AI モデルをダウンロードする

チャット用

```bash
ollama pull hf.co/alfredplpl/gemma-2-2b-jpn-it-gguf
```

エンべディング用

```bash
ollama pull kun432/cl-nagoya-ruri-base
```

## コンテナの起動

```bash
docker compose up -d
```

### 初回起動時の設定変更

searxng/settings.yml に JSON フォーマットを追加する

```yaml
...
  formats:
    - html
    - json  # 追加
...
```

再起動する

```bash
docker compose down
docker compose up -d
```
