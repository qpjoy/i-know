# i-know

I know i-know

# verions

```json
{
  "node": "v20.18.1",
  "npm": "10.8.2",
  "pnpm": "9.14.4",
  "rush": "rush-5.147.0"
}
```

```bash
npm install -g @microsoft/rush --loglevel verbose

git clone git@github.com:qpjoy/i-know.git
rush init

git add .
git commit -m "Initial commit"

# ~~~ git blame
# ~~~ git bisect

rush update
# 更新所有package.json中的文件到最新版本
rush update --full
# 更改pnpm-version 或 设置
rush update --full --purge

# !!! 重新安装 rush update --purge
rush rebuild --verbose

# 安装所有依赖B，但是不包括B的项目
rush build --to-except B
# Build only B and nothing else
rush build --only B
# 重新安装两个项目 和 依赖这两个的所有项目
rush rebuild --to widget --to widget-demo
# 重装这个库 和 所有依赖这个库的项目 和 所有 依赖这些项目的(树状有依赖)
rush rebuild --from widget

# "~1.2.3"
rush add --package example-lib@1.2.3
# "^1.2.3"
rush add --package example-lib@1.2.3 --caret
# update all example-lib
rush add --package example-lib@1.2.3 --make-consistent


rush remove --package example-lib

rush upgrade-interactive

# clean state
rush unlink
rush purge

# lib/my-toolchain


# de use install-run-rush
node common/scripts/install-run-rush.js --help
node common/scripts/install-run-rush.js install

# commit-msg

# prettier
rush init-autoinstaller --name rush-prettier
cd common/autoinstallers/rush-prettier
pnpm install prettier pretty-quick
rush update-autoinstaller --name rush-prettier

# pack tgz包
rush publish --pack --include-all --publish --release-folder releases/release-fe
# 确保有该target分支
rush publish --apply --target-branch main
```

# 添加 npm 用户

```bash
npm adduser
npm profile enable-2fa auth-and-writes
```

### usage

先 git add、commit，然后 rush change 会基于 repo url，对比本地和远端的子项目有没有更改。然后建议各个项目是否生成 change log,最后 rush publish --apply --target-branch
