## Useful Powershell commands

- show .net assembly manifest
    - `([system.reflection.assembly]::loadfile("C:\code\Kno2\src\Inofile.Worker\bin\Debug\Microsoft.Extensions.Logging.Abstractions.dll")).FullName`

- show environment variables
    - `Get-ChildItem Env:`

- show entries in PATH variable
    - `$env-path -split ";"

- list events of system restart from event log
    - `get-eventlog -logname system -source user32 | select timegenerated, message`
    - to organize by message add a sort clause at the end
    - `get-eventlog -logname system -source user32 | select timegenerated, message | sort message`
    - Reference:
        - https://devblogs.microsoft.com/scripting/use-powershell-to-parse-event-log-for-shutdown-events/
- show version of PowerShell
    - `get-host`

- find text in files in current folder, recursive
    - `Get-ChildItem -Recurse | Select-String "dummy" -List | Select Path`
