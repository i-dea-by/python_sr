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

## How-to use in pyenv-win

Execute in Windows Terminal (or PowerShell)
```
$Env:PYTHON_BUILD_MIRROR_URL="https://python-sr.dea.by/"
$Env:PYTHON_BUILD_MIRROR_URL_SKIP_CHECKSUM=1
pyenv update
```
After installing the required versions, re-enter (close and open) the console and execute `pyenv update` to download the default mirrors

> [!CAUTION]
> Some antiviruses on VirusTotal find a virus in the created installers... I don't know how to overcome this - I will be glad to receive advice (:

## Updates

### 2024-09-18

- Python 3.10.15 security release
- Python 3.11.10 security release
