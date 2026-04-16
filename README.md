# Massimult Language Server Extension

A Visual Studio Code extension that enables Massimult language server on massimult (.lm) source files.

## Requirements

`massimult-lsp` must be available locally.

## Building and Installing the extension

```sh
npm install
./sync-engine-version.sh update-in-place
npm install
rm -f *.vsix
version=$(jq -r '.version' package.json)
npm run lint
npm run compile
npm run esbuild
vsce package
code --install-extension "massimult-lsp-${version}.vsix" --force
```

## Configuring the extension

To configure the command used to start the Massimult language server, `massimult-lsp` by default, go to `Settings` and search for `massimult`.

## Debugging the extension

- Run `npm install` in this folder
- Open VS Code on this folder
- Press `Ctrl+Shift+D` / `Cmd+Shift+D` to reveal the everything Debug viewlet
- Select `Launch Client` from the drop down
- Run the launch config
