# Typescript のランタイム環境

なんの変哲もない、ただただ Typescript を実行して動作確認するためだけの環境です。

## 環境構築

基本 docker。
Typescript を放り込むときだけ、docker exec で中に入って、npm をたたいた。

```
docker-compose exec node /bin/bash
npm install --no-bin-link ts-node
npm install --no-bin-link typescript
```

docker を止めると tsc コマンドが効かなくなるので、
/usr/local/bin の下にシンボリックリンクを作っておく。

```
docker-compose exec node /bin/bash
cd /usr/local/bin
ls -s /usr/src/app/node_modules/typescript/bin/tsc
```

## 実行

docker の中に入って行う。

```
docker-compose exec node /bin/bash
tsc Typescriptファイル
node JSにコンパイルされたTSファイル
```
