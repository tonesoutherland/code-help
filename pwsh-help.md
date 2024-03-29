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

### Environment Variables
- Show vars (sort by name)
    - `get-childitem -path env:* | sort-object name`
- Add var
    - `$Env:[varname] = "[varvalue]"`
- Remove var
    - `[Environment]::SetEnvironmentVariable("[varname]", $null, "Machine")`


## Config

- set oh-my-posh theme
    - run `code $PROFILE` in a powershell prompt
    - edit this line:
    	- `oh-my-posh init pwsh --config "$env:POSH_THEMES_PATH\multiverse-neon.omp.json" | Invoke-Expression`
    - change `.omp.json` filename to switch to a new theme
    - select themes from: https://ohmyposh.dev/docs/themes
    - install desired font: https://ohmyposh.dev/docs/installation/fonts
