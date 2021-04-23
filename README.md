# emfreeze
Emfreeze is a command line tool for Windows to freeze a virtual environment as a standalone package. Contrary to cx_freeze or PyInstaller, emfreeze produces no additional executables. Instead it packs your scripts and dependencys together with the according python embeddable package. Therefore it is not good for standalone Python applications but ideal for an embedded use of Python inside another application. The main benefit is that the chance of implications with anti-virus software is reduced, because your freezed package only contains signed and commonly known executables.  
  
**Warning**: 
Emfreeze does not hide your source code in any way. The most it will do is to compile your python entry points to pyc files, which can be easily decompiled.
## Installation
```
pip install emfreeze
```

## Usage
Inside of your virtual environment execute the emfreeze over the command line.
```
emfreeze
```
Emfreeze will download the according Python runtime and copys it along with your python entry points, site-packages and any directory beside the `Include` and the `Scripts` directory in the dist directory. 

### Additional arguments
```
usage: emfreeze [-h] [-d PATH] [--embeddable-package PATH] [-c] [--post-build-script PATH]

Emfreeze freezes a python virtual environment together with the python embeddable package, to make it easy to embed it into other software without creating executables.

optional arguments:
  -h, --help            show this help message and exit
  -d PATH, --dist-path PATH
                        Set the path of the final build
  --embeddable-package PATH
                        Path of a compatible python embeddable package zip file, if emfreeze should not download it
  -c, --compile         Compile your toplevel scripts
  --post-build-script PATH
                        Path of a executable script (e.g. Batch-Script) which executes inside your newly build package.
```
## Requirements and Troubleshooting
Emfreeze works obviously only with Python versions which have an embeddable package version. If this is an issue or if you experience other issues related to the embeddable package Python distribution, you can replace the runtime via the `--embeddable-package` argument. Just download a different distribution and zip it.

## Licensing
Emfreeze is MIT licensed. But since there is no part of emfreeze inside your distributed build, you don't have to worry about that. Keep in mind that Python and your dependencys have their own licenses, so please keep that in mind.