#LDVSC

LDVSC is a Docker based Laravel development environment for use with VS Code's Docker remote feature.

## Install

The recommended way of installing the environment is to add it clone it into your project:

```
git clone git@github.com:blackfyre/ldvsc.git .devcontainer
```
The important bit here is the `.devcontainer` directory designation! This is what VSCode will take notice of!

## How to use

To use the environment, you'll have to have:

 * Docker installed
 * VS Code installed with the `ms-vscode-remote.remote-containers` extension

If all these are met, after opening your project in VSCode, it will offer you the option to re-open the project in the container.