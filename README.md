# `ffprobe-static-electron`

The module returns a file path to the binary for the target operating system. 

It is a modified version from the original [ffprobe-static](https://github.com/pietrop/ffprobe-static) to use [`electron-builder` file macros  in `package.json`, where OS name are `mac`, `linux` or `win`](https://www.electron.build/file-patterns/#file-macros)

In `ffprobe-static`, recognising the target OS is done with [`os.platform()`](https://nodejs.org/api/os.html#os_os_platform) where mac os x is  recognised as`darwin` rather then `mac`.

The need to tailor ffmpeg-static to use with `electron-builder` came from a use cases such as that of [autoEdit.io](http://autoEdit.io). 

<!-- I've also added `browser`, as a platform option, for use case when module is use client side, eg bundled using browserify.-->



---

Static binaries for `ffprobe`. OSX only at the moment, please send a PR if you would like to help with adding support for other platforms.

Based on <https://github.com/eugeneware/ffmpeg-static>.

Binaries are from <http://ffmpeg.zeranoe.com/builds/>

## Installation

This module is installed via npm:

``` bash
$ npm install ffprobe-static-electron
```

## Usage

```js
var ffprobe = require('ffprobe-static-electron');
console.log(ffprobe.path);
```

Version Notes
----

Currently supports Mac OS X (64-bit), Linux (32 and 64-bit) and Windows
(32 and 64-bit).

Currently version `3.1` is installed for Mac and Linux, and `3.0.1` for
Windows.

I pulled the versions from the ffmpeg static build pages linked from the
official ffmpeg site. Namely:

* [64 bit Mac OSX](https://evermeet.cx/ffmpeg/)
* [64 bit Linux](http://johnvansickle.com/ffmpeg/)
* [32 bit Linux](http://johnvansickle.com/ffmpeg/)
* [64 bit Windows](http://ffmpeg.zeranoe.com/builds/win64/static/)
* [32 bit Windows](http://ffmpeg.zeranoe.com/builds/win32/static/)

Acknowledgements
----

Special thanks to [eugeneware](https://github.com/eugeneware) for <https://github.com/eugeneware/ffmpeg-static>, which this is based upon.
