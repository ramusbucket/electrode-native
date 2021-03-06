## `ern add <dependency>`
#### Description
* Add the dependency to the MiniApp package.json when all checks pass

#### Syntax
`ern add <dependency>`

**Options**  
`--dev/-d`

* Add the dependency to the MiniApp package.json `devDependencies`  
* Checks are not performed to add development dependencies  

`--peer/-p`

* Add the dependency to the MiniApp package.json `peerDependencies`  
* Checks are not performed to add peer dependencies

#### Remarks
* The `ern add <dependency>` command is the `ern` equivalent of `yarn add` and `npm install`
When you work with a MiniApp, always use `ern add` to add packages in place of `yarn add` or `npm install`.

* The `ern add <dependency>` command runs `yarn add` and it performs important additional compatibility checks.

* You don't need to specify an explicit version for a package that you add using `ern add`. If you add an explicit version for a package, it is ignored.

* If the package is declared in the current platform manifest, then the version from the manifest is used.  

* The `ern add <dependency>` command performs the following checks:  
 - If the package is declared in the manifest, then `ern` installs the package at the version declared in the manifest.
 - If the package is not declared in the manifest, then additional checks are performed:
    - If the package contains native code in any way (the package itself is a native module or it transitively contains one or more native dependencies, the command denies the package installation until a configuration is added to the manifest for this package.
    - If the package contains only JavaScript code, then the command proceeds with the package installation without further checks.  
-------
