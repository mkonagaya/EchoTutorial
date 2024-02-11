## 初回

初回は、go.modが作られていないため、手動で初期化が必要

### Dockerfileでコメントアウトするもの
- `RUN go mod init main`
- `RUN go mod tidy`
- `CMD ["go", "run", "main.go"]`

### 初期化
`docker compose exec app bash`でコンテナに入り
```bash
go mod init main
go mod tidy
...
```
と入れて、マウントされたローカルに`go.mod`が入ってくる。

初期化が完了したらコメントアウトを解除して、リビルド、再起動。


