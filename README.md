# WPM
A new Node Package Manager - design it based on Java Maven Design Principles.

**Remeber, it is draft stage till now.**

# Features
+ Manage all Packages globally, integrating all modules in one folder to *Globally `node_modules` folder*.
+ Make your local project smaller and smaller.
+ Compatible with `yarn` and `npm`.

# Details
1. **Do not have the local folder `node_modules` in local project path anymore.** - intead of, it be installed globally and be import from the globally `/root/.wpm/node_modules`, but i have not ready to thinkof where to put the all dependencies in globally file system.
2. **`import` and `require` all from globally dependencies folder.** - Does not need to import from locally `node_modules` folder.

# TODOs
- [x] Start design `WPM`.
- ~~[-] Can i only use a webpack plugin to impls it? thinking...~~
    - From this link [nodejs/api/modules_loading_from_the_global_folders](https://nodejs.org/api/modules.html#modules_loading_from_the_global_folders) i found we do not need modify any source code of `Node` or `npm`, we only install all packages globally, and import this nodeJS will done that automatically. Because of the native `module` system of Node be designed very flexible.
    - so the next question is, If has new dependency package in project, how to install it globally? I don't know is there any package manager supports that? I need some time to resolve it and find a good resolution or impls it by myself finally.
- [ ] Implements `WPM` CLI.
    - [ ] command `wpm config [options]`, config options includes *registry*, *prefix*, *config*, *init*
    - [ ] command `wpm init` - Just impls it like `npm init`. 
    - [ ] command `wpm install`
    - [ ] command `wpm remove`, alias `rm`, `delete`, `del`
- [ ] Implements `NodeJS` extensions to make it supports `import`、`require` collect dependencies from globally folder first.
- [ ] Publish & Open Source

# References
+ [nodejs/api/modules_loading_from_the_global_folders](https://nodejs.org/api/modules.html#modules_loading_from_the_global_folders)

# LICENSE
Before i done the all of `TODOs`, It was under [Apache License, Version 2.0, January 2004](https://www.apache.org/licenses/LICENSE-2.0)* license, After that it will releases under [MIT](https://opensource.org/licenses/MIT) license.
