# 神奈川県版 新型コロナウイルス感染症対策サイト

![](https://github.com/tokyo-metropolitan-gov/covid19/workflows/production%20deploy/badge.svg)

<img src="static/ogp.png" width="400">

## ライセンス

### 東京都
* [東京都 新型コロナウイルス感染症対策サイト](https://stopcovid19.metro.tokyo.lg.jp/)
* [GitHubサイト](https://github.com/tokyo-metropolitan-gov/covid19/)

```
Copyright 2020 Tokyo Metropolitan Government
Released under the MIT license
https://github.com/tokyo-metropolitan-gov/covid19/blob/master/LICENSE.txt
```

### 北海道
* [北海道 新型コロナウイルス感染症対策サイト](https://stopcovid19.hokkaido.dev/)  
* [GitHubサイト](https://github.com/codeforsapporo/covid19)

```
Released under the MIT license
https://github.com/codeforsapporo/covid19/blob/development/LICENSE.txt
```


## How to Contribute / 貢献の仕方
[Kanagawa Issues](https://github.com/openkawasaki/covid19/issues) にあるいろいろな修正にご協力いただけると嬉しいです。

オープン川崎のSlackの#prj_covid19チャンネルでも情報共有を行っています。加入は[こちらからどうぞ](https://join.slack.com/t/openkawasaki/shared_invite/zt-4hbuav6c-Ttza18ObLreA6JZ6mvcyIw)


その他の詳しい情報は[How to contribute(東京版)](https://github.com/tokyo-metropolitan-gov/covid19/blob/development/.github/CONTRIBUTING.md)を御覧ください。

All contributions are welcome!
Please check [How to contribute](https://github.com/tokyo-metropolitan-gov/covid19/wiki/How-to-contribute) for details.

## License / ライセンス
本ソフトウェアは、MITライセンスの元提供されています。 
This software is released under the MIT License.

## For Developers / 開発者向け情報

### How to Set Up Environments / 環境構築の手順

#### Use yarn / yarn を使う場合**
``` bash
# install dependencies
$ yarn install

# serve with hot reload at localhost:3000
$ yarn dev
```

#### Use docker / docker compose を使う場合
```bash 
# serve with hot reload at localhost:3000
$ docker-compose up
```

* `docker-compose up` 初回実行時に下記のエラーが出た場合

```
yarn run v1.21.1
$ cross-env NODE_ENV=development nuxt-ts
covid19 | /bin/sh: cross-env: not found
error Command failed with exit code 127.
info Visit https://yarnpkg.com/en/docs/cli/run for documentation about this command.
covid19 exited with code 127
```

なんらかの理由で`yarn install`が失敗していると考えられるので、下記を実行後、再度 `docker-compose up` してみてください。

```bash
$ docker-compose exec app sh
/app # yarn install
/app # exit
```

#### Use npm / npm を使う場合
``` bash
# install dependencies
$ npm install

# serve with hot reload at localhost:3000
$ npm run dev
```

### Deployment to Staging & Production Environments / ステージング・本番環境への反映

**TBD**
