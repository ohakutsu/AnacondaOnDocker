# 研究室の共用パソコン用のAnaconda環境
https://github.com/ohakutsu/AnacondaOnDocker

## 使い方

1. イメージのビルド

```
docker build -t {イメージ名} .
```

2. コンテナを作成
```
docker run -it -d --name {コンテナ名} -v {ホスト側のフルパス}:/work -p 8000:8000 {イメージ名}
```

3. コンテナに潜入

```
docker ps
# コンテナIDを確認

docker exec -it {コンテナID} /bin/bash
```

4. jupyter-notebookを起動

```
jupyter-notebook --port 8000 --ip=0.0.0.0 --allow-root
```

5. 表示されるリンクを開く
```
http://127.0.0.1:8000/?token=41a26248c5239af92a8........94f8126017c55b9504476
```
