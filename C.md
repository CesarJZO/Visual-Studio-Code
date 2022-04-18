# C

## Appearance

- In `setting.json`

```json
{
  "workbench.colorTheme": "GitHub Dark Default",
  "workbench.iconTheme": "seti"
}
```

## Compiler

### Windows

- Install MinGW-x64 via [MYSYS2](https://www.msys2.org/)
- Add its location `C:\msys64\mingw64\bin` to `PATH`
- Check if it is installed

```powershell
> g++ --version
> gcc --version
```

- Create `tasks.json`

```json
{
  "tasks": [
    {
      "type": "cppbuild",
      "label": "C/C++: g++.exe build active file",
      "command": "C:/msys64/mingw64/bin/g++.exe",
      "args": [
        "-g",
        "${file}",
        "-o",
        "${workspaceFolder}\\bin\\${fileBasenameNoExtension}.exe"
      ],
      "options": {
        "cwd": "${fileDirname}"
      },
      "problemMatcher": ["$gcc"],
      "group": {
        "kind": "build",
        "isDefault": true
      },
      "detail": "compiler: C:/msys64/mingw64/bin/g++.exe"
    }
  ],
  "version": "2.0.0"
}
```

- In `settings.json`

```json
{
  "files.associations": {
    "*.h": "c"
  }
}
```

### Linux

- Install GNU C Compiler

```bash
$ sudo apt install build-essential
```

- Create `tasks.json`

```json
{
  "version": "2.0.0",
  "tasks": [
    {
      "type": "shell",
      "label": "gcc build active file",
      "command": "/usr/bin/gcc",
      "args": ["-g", "${file}", "-o", "~/bin/${fileBasenameNoExtension}"],
      "options": {
        "cwd": "/usr/bin"
      },
      "problemMatcher": ["$gcc"],
      "group": {
        "kind": "build",
        "isDefault": true
      }
    }
  ]
}
```

- In `settings.json`

```json
{
  "files.associations": {
    "*.h": "c"
  }
}
```

## Git ignore

```gitignore
.vscode/
out/
bin/
executables/
```

## Sources

- [C/C++ for Visual Studio Code](https://code.visualstudio.com/docs/languages/cpp)
