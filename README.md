# LDVSC

LDVSC is a Docker based Laravel development environment for use with VS Code's Docker remote feature.

## In a bit more detail

VSCode offers a way to manage Docker containers for development. With this feature, you can keep your host system relatively free of just about programming languages and their attached clutter. Providing you with a portable development environment!

This package builds an environment built for Laravel application development with:

* Nginx web server
* Latest MySQL + phpMyAdmin
* PHP 7.4 with composer
* Redis + phpRedMin
* Mailhog
* Node 12 + yarn

It also adds a few VSCode plugins ment for php development to your remote instance (this wont negatively effect your host VSCode):

 * `bmewburn.vscode-intelephense-client`,
 * `eamodio.gitlens`,
 * `EditorConfig.EditorConfig`,
 * `mikestead.dotenv`,
 * `ms-azuretools.vscode-docker`,
 * `onecentlin.laravel-blade`,
 * `redhat.vscode-yaml`,
 * `wongjn.php-sniffer`

## Install

The recommended way of installing the environment is to add it clone it into your project:

```
git clone --depth=1 git@github.com:blackfyre/ldvsc.git .devcontainer
// Optional: clean git information
rm -rf .devcontainer/.git*
```
The important bit here is the `.devcontainer` directory designation! This is what VSCode will take notice of!

## How to use

To use the environment, you'll have to have:

 * Docker installed
 * VS Code installed with the `ms-vscode-remote.remote-containers` extension

If all these are met, after opening your project in VSCode, it will offer you the option to re-open the project in the container.
