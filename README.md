# setup-pyside6-win7

[![Test composite action](https://github.com/LorenEteval/setup-pyside6-win7/actions/workflows/test.yml/badge.svg?branch=main)](https://github.com/LorenEteval/setup-pyside6-win7/actions/workflows/test.yml)

GitHub action that sets up a Windows7–compatible version of PySide6.

## Usage

```yaml
- name: Setup PySide6 for Windows7  
  uses: LorenEteval/setup-pyside6-win7@v1
  with:
    # required: PySide6 version
    pyside6-version: "6.8.3"
    # optional: x86 or x64, default is x64
    architecture: x64
    # optional: PySide6 relative library path, default is Lib/site-packages
    relative-lib-path: Lib/site-packages
    # optional: setup PySide6 for windows7 from this repo
    github-repo: crystalidea/qt6windows7
    # optional: release tag for the github repo, default is v{{ inputs.pyside6-version }}
    release-tag: v6.8.3
- name: Check PySide6 for Windows7 version
  shell: bash
  run: |
    python -c "import sys; print(sys.version)"
    python -c "import PySide6; print(PySide6.__version__)"
```
