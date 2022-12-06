## Useful Powershell commands

- show .net assembly manifest
    - `([system.reflection.assembly]::loadfile("C:\code\Kno2\src\Inofile.Worker\bin\Debug\Microsoft.Extensions.Logging.Abstractions.dll")).FullName`