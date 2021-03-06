# DEPRECATED
 * THIS PROJECT IS BEING REINTEGRATED TO [MAIN PROJECT](https://github.com/fade-project/fade).
 * NO FURTHER UPDATES.

# deb-build
 * Build a Debian package in javascript code

## Notice
 * This project is subproject of FADe Project
 * Internally used by FADe, Licensed under same license of FADe.

## Usage:
 * Install Project:
```
 $ npm install @fade-project/deb-build
```
 * require() in your project:
```
var deb = require('@fade-project/deb-build')
```
 * deb.types
   * Currently, it has systemd, isolated, normal. Please refer FADe Project docs.
 * deb.set_data_tar_gz_datadir()
   * It'll return an tmpjs' dir object. deb-build will Build data.tar.gz based on this directory.
 * deb.get_data_tar_gz_datadir()
   * Same output with set_data_tar_gz_datadir(), but It won't (re)set object.
 * deb.generate_ar_header(filename, timestamp, owner_id, group_id, filemode, filesize)
   * It'll return 60-byte Buffer. It generates each file's header in ar archive.
 * deb.build(name, version, desc, url, architecture, depends, priority, run, maintainer_name, maintainer_email, type, postinst_payload, prerm_payload)
   * You can disable Depends field by set depends parameter to "none"
   * It'll return full debian binary. Accept parameters as a String (except some parameters, see below).
   * It accept "depends" parameter as a comma-space separated String or an Array.

## Credit
 * [targz](https://github.com/miskun/targz) - [MIT License](https://github.com/miskun/targz/blob/master/LICENSE)
 * [tar-stream](https://www.npmjs.com/package/tar-stream) - [MIT License](https://github.com/mafintosh/tar-stream/blob/master/LICENSE)
 * [tmp](https://github.com/raszi/node-tmp) - [MIT License](https://github.com/raszi/node-tmp/blob/master/LICENSE)
 * [rimraf](https://github.com/isaacs/rimraf) - [ISC License](https://github.com/isaacs/rimraf/blob/master/LICENSE)
 * Special thanks to [wikipedia:en:ar (Unix)](https://en.wikipedia.org/wiki/Ar_%28Unix%29)
 * Special thanks to [naholyr for sysvinit service ref](https://gist.github.com/naholyr/4275302)
