1

    # not pnpm init
    add .gitignore
    add package.json
    add pnpm-workspace.yaml

    mkdir try/api try/general -p
    pnpm init in two dirs

    # root dir
    pnpm i axios -F api
    pnpm i api -F general --workspace # --workspace 仅添加在 workspace 找到的依赖项。installed from the workspace
    # pnpm i api -F general # installed from the registry

2

    mkdir feel/next feel/nest -p

    copy files from mark-start/start-next
    change package.json name renamed next
    remove lock file

    copy files from mark-start/start-nest
    change package.json name renamed nest
    remove lock file

    pnpm i
    pnpm -F nest start:dev
    pnpm -F next dev

version

    pnpm 7.28.0
    node v16.13.1
    npm 8.1.2

package.json

```
{
  "name": "root",
  "private": true,
  "scripts": {
    "preinstall": "npx only-allow pnpm"
  }
}
```

pnpm-workspace.yaml

```
packages:
  - 'try/*'
  - 'feel/*'
```

.gitignore

```
node_modules/
```
