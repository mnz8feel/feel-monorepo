1

    lerna init -i
    # pnpm init -h
    delete "workspaces" field in package.json
    Set `"npmClient": "pnpm"` and `"useWorkspaces": true` in `lerna.json`.
    add pnpm-workspace.yaml
    pnpm i

    mkdir packages/api-center # lerna create 生成多余信息太多，还有 git 初始化等
    cd packages/api-center
    pnpm init

2

    # init general
    mkdir packages/general
    cd packages/general
    pnpm init

    # installed from the registry
    pnpm i axios -F api-center

    # installed from the workspace
    pnpm i api-center -F general # "api-center": "workspace:^0.0.1" in packages\general\package.json

3

    # init feel-next
    pnpm i next react react-dom -F feel-next
    add scripts to feel-next package.json

        "dev": "next dev",
        "build": "next build",
        "start": "next start",
        "lint": "next lint"

    add the pages/index.js
    lerna --scope feel-next run dev
    # add typescript
    create an empty `tsconfig.json` file in the feel-next root folder
    lerna --scope feel-next run dev

4

    mkdir feel-nest
    copy files from mark-start/start-nest
    pnpm i

5

    pnpm -F feel-next dev # <=> lerna --scope feel-next run dev
    # maybe just pnpm is enough
    remove lerna

version

    pnpm 7.28.0
    node v16.13.1
    npm 8.1.2

pnpm-workspace.yaml

```
packages:
    - 'packages/*'
```
