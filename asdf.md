<!--
title: 'asdf.md'
author: 'Elias Albuquerque'
created: '2023-11-30'
update: '2024-05-04'
-->


# asdf manager

**asdf** is an extendable version manager that supports multiple languages. It 
allows you to easily install, manage, and switch between different versions of 
various tools and runtimes, such as Node.js, Ruby, Python, and many others.

asdf supports: Linux, MacOS and Windows (via WSL2 or via Docker).


- [Introduction](#introduction)
- [Search the plugin](#search-the-plugin)
- [Commands](#commands)


## Introduction

- [Guide](https://asdf-vm.com/guide/introduction.html)
- [github.com/asdf](https://github.com/asdf-vm/asdf)


## Search the plugin

- [Plugins](https://github.com/asdf-vm/asdf-plugins)

Exemple: 

- Installing **php** plugin:

    ```terminal
    asdf plugin-add php https://github.com/asdf-community/asdf-php.git
    ```


## Commands

- https://asdf-vm.com/manage/commands.html

1. List:

   ```terminal
   asdf list						--> list all plugins installed,
   asdf list nodejs					or, list all versions of a given plugin.
   ```

2. Install plugin:

    ```terminal
    asdf plugin add nodejs			--> add plugin example.
    ```

3. Install version:

    ```terminal
    asdf list-all nodejs			--> list all version available for install.
    asdf install nodejs 20.3.1		--> install last version,
    asdf install nodejs latest			or, get the latest version available,
    asdf install nodejs latest:16		or, get the 16. latest version available.
    asdf install nodejs 16.13.2		--> install old version.
    ```

4. Run in local project:

    ```terminal
    asdf local nodejs 16.13.2		--> choose the "global" version in local project.
    ```

5. Uninstall a version

    ```terminal
    asdf uninstall nodejs 16.13.2	--> uninstall the specific version,
    asdf uninstall nodejs latest		or, the latest one.
    ```

6. Updating

    ```terminal
    asdf plugin update --all		--> update plugins.
    asdf update						--> update the asdf.
    ```
