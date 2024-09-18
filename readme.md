# Unofficial Python security releases installers (x86, x64) for Windows

**Reason:** ability to install python security releases in pyenv-win.

But unfortunately, pyenv-win does not yet support installation from releases as it is done for graalpython/releases.

So I made my own mirror: [python-sr.dea.by](https://python-sr.dea.by)

All releases posted here will be duplicated on my mirror.

## Achtung and alarma :)

With each release, a file of the type "XX.XX.XX_release.md" is posted, which contains the name of the file, its sha256 checksum and a link to VirusTotal.

Example:
- python-3.10.15-amd64.exe:
  - sha256: e73c2fc40cef1acaaf76a6ccd9a7cd738100bb9d6905ef1f71ce581793bdb0b9
  - [VirusTotal](https://www.virustotal.com/gui/file/e73c2fc40cef1acaaf76a6ccd9a7cd738100bb9d6905ef1f71ce581793bdb0b9)

You can also check the files from the mirror on VirusTotal, they should be the same :)

> [!CAUTION]
> Some antiviruses on VirusTotal find a virus in the created installers... I don't know how to overcome this - I will be glad to receive advice (:

## How-to use in pyenv-win

Execute in Windows Terminal (or PowerShell)
```
$Env:PYTHON_BUILD_MIRROR_URL="https://python-sr.dea.by/"
$Env:PYTHON_BUILD_MIRROR_URL_SKIP_CHECKSUM=1
pyenv update
```
After installing the required versions, re-enter (close and open) the console and execute `pyenv update` to download the default mirrors

## How-to build installer for Python security release

Let's do this using the example of the version Python 3.11.10

> [!IMPORTANT]
> Actually, all this is written in "Python-3.11.10\Tools\msi\README.txt"

1. Download sources: Gzipped or XZ compressed source tarball - for example https://www.python.org/ftp/python/3.11.10/Python-3.11.10.tgz
2. Unpack: if use WinRAR - select "Extract here..." in context menu (right click on file). If use 7zip - twice - at first unpacked Python-3.11.10.tar file, and then unpack it here
3. Goto to "Python-3.11.10\Tools\msi\" and call from commandline `buildrelease.bat -x64`

> [!WARNING]
> Most likely, you will also need to install the required version of Visual Studio build tools

4. After finishing, the python installer files will be at "Python-3.11.10\PCbuild\amd64\en-us\"



## Updates

### 2024-09-18

- Python 3.10.15 security release
- Python 3.11.10 security release
