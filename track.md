1

    lerna init -i
    pnpm init -h
    delete "workspaces" field in package.json
    Set `"npmClient": "pnpm"` and `"useWorkspaces": true` in `lerna.json`.
    add pnpm-workspace.yaml

    mkdir packages/api-center # lerna create 生成多余信息太多，还有 git 初始化等
    cd packages/api-center
    pnpm init

2

    # init general ui-center api-center
    cd packages\general
    pnpm init

    # installed from the registry
    pnpm i axios -F api-center

    # installed from the workspace
    pnpm i api-center -F general # "api-center": "workspace:^0.0.1" in packages\general\package.json
