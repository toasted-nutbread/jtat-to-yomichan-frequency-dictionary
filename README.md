# About

This repository contains the source code of a script which is used to generate a frequency dictionary 
from a file created by [Japanese Text Analysis Tool](https://sourceforge.net/projects/japanesetextana/)
for use with [Yomichan](https://github.com/FooSoft/yomichan).

## Usage

A node script is used to generate the dictionary data:

```sh
node main.js path/to/jtat-output.txt ./output
```

The data can then be added to a .zip archive using any software.
The example below uses the 7z command line executable to generate the archive:

```sh
7z a -tzip -mx=9 -mm=Deflate -mtc=off -mcu=on jtat-freqnecy-dictionary.zip ./output/*.json
```

The title of the dictionary will use the file name of the JTAT input file.
This title can be changed by editing the `index.json` file's `"title"` field
before generating the .zip archive.
