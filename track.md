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

    lerna --scope feel-next run dev
    # add typescript
    create an empty `tsconfig.json` file in the root folder
    lerna --scope feel-next run dev

version

    pnpm 7.28.0

pnpm-workspace.yaml

```
packages:
    - 'packages/*'
```
