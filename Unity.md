# Unity

## Prerequisites

- [.NET Framework](https://dotnet.microsoft.com/download/dotnet-framework/net471) (Windows)
- [Analyzers](https://www.nuget.org/packages/Microsoft.Unity.Analyzers/)

## Global

- Extract the analyzers to `%USERPROFILE%\.omnisharp`
- In the same directory, create a `omnisharp.json` file:

```json
{
  "RoslynExtensionsOptions": {
    "EnableAnalyzersSupport": true,
    "LocationPaths": [
      "./microsoft.unity.analyzers.1.13.0" // Version may vary
    ]
  }
}
```

- In `settings.json`

```json
{
  "omnisharp.path": "c:\\Users\\cesar\\.vscode\\extensions\\ms-dotnettools.csharp-1.24.4-win32-x64\\.omnisharp\\1.38.2\\OmniSharp.exe"
}
```

## Per project

- Create an `.editorconfig` file:

```editorconfig
root=true

[*.cs]
dotnet_diagnostic.IDE0051.severity = silent
dotnet_diagnostic.IDE0044.severity = silent
```

## Git ignore

```
[...]

# Visual Studio cache directory
.vs/
.vscode/
.vsconfig
.editorconfig

[...]
```

## Sources

- [Unity Development with VS Code](https://code.visualstudio.com/docs/other/unity)
