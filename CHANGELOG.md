# node-pre-gyp changelog

## 0.5.5

 - Improved binary validation that also now works with node-webkit (@Mithgol)
 - Upgraded test apps to work with node v0.11.x
 - Improved test coverage

## 0.5.4

 - No longer depends on external install of node-gyp for compiling builds.

## 0.5.3

 - Reverted fix for debian/nodejs since it broke windows (#45)

## 0.5.2

 - Support for debian systems where the node binary is named `nodejs` (#45)
 - Added `bin/node-pre-gyp.cmd` to be able to run command on windows locally (npm creates an .npm automatically when globally installed)
 - Updated abi-crosswalk with node v0.10.26 entry.

## 0.5.1

 - Various minor bug fixes, several improving windows support for publishing.

## 0.5.0

 - Changed property names in `binary` object: now required are `module_name`, `module_path`, and `host`.
 - Now `module_path` supports versioning, which allows developers to opt-in to using a versioned install path (#18).
 - Added `remote_path` which also supports versioning.
 - Changed `remote_uri` to `host`.

## 0.4.2

 - Added support for `--target` flag to request cross-compile against a specific node/node-webkit version.
 - Added preliminary support for node-webkit
 - Fixed support for `--target_arch` option being respected in all cases.

## 0.4.1

 - Fixed exception when only stderr is available in binary test (@bendi / #31) 

## 0.4.0

 - Enforce only `https:` based remote publishing access.
 - Added `node-pre-gyp info` command to display listing of published binaries
 - Added support for changing the directory node-pre-gyp should build in with the `-C/--directory` option.
 - Added support for S3 prefixes.

## 0.3.1

 - Added `unpublish` command.
 - Fixed module path construction in tests.
 - Added ability to disable falling back to build behavior via `npm install --fallback-to-build=false` which overrides setting in a depedencies package.json `install` target.

## 0.3.0

 - Support for packaging all files in `module_path` directory - see `app4` for example
 - Added `testpackage` command.
 - Changed `clean` command to only delete `.node` not entire `build` directory since node-gyp will handle that.
 - `.node` modules must be in a folder of there own since tar-pack will remove everything when it unpacks.

