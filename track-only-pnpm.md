1

    # not pnpm init
    add .gitignore
    add package.json
    add pnpm-workspace.yaml

    mkdir try/api -p
    cd try/api
    pnpm init
    # root dir
    pnpm i axios -F api

    mkdir try/general
    cd try/general
    pnpm init
    # root dir 如果没有 pnpm-workspace.yaml, installed from the registry, not installed from the workspace
    pnpm i api -F general

        no pnpm-workspace.yaml in general's package.json : "api": "^5.0.7"

    mkdir feel/next -p
    cd feel/next
    pnpm init
    # root dir
    pnpm i next react react-dom -F next

    add scripts to next package.json

        "dev": "next dev",
        "build": "next build",
        "start": "next start",
        "lint": "next lint"

    pnpm -F next dev
    # add typescript
    create an empty `tsconfig.json` file in the next root folder
    pnpm -F next dev

    mkdir nest
    copy files from mark-start/start-nest
    pnpm i

version

    pnpm 7.28.0
    node v16.13.1
    npm 8.1.2

在没有 `pnpm-workspace.yaml` 文件时，依然可以 `pnpm i axios -F api` `pnpm i next react react-dom -F next`

pnpm-workspace.yaml

```
packages:
  - 'try/*'
  - 'feel/*'
```

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

.gitignore

```
node_modules/
```
