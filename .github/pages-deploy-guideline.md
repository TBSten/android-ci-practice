# Github Pages Deploy Guideline

## ディレクトリ構成

以下の構成で

```
base-url/
    pr-xx/      ... #xxのPull Requestに関するレポートを出力するディレクトリ
        kover/
        ktlint/
        androidLint/
```

## concurrency group

pages への deploy を伴う job には以下を設定することとする。これにより、重複してデプロイが走っても順番に走るようになる。

```yaml
concurrency:
  group: "github-pages-deploy"
  cancel-in-progress: false
```
