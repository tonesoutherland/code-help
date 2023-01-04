## Choco clean cache
The paid version of chocolately will clean cache automically, but there is a work-around for the free version.

- Install choco package

    - `choco install choco-cleaner`

- Set the execution policy in Powershell to unrestricted, but only temporarily. Normal setting is RemoteSigned

    - `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`

- Run the ps1 script

    - `c:\tools\BCURRAN3\choco-cleaner.ps1`

- You should see output simliar to the following:

<pre>
Choco-Cleaner.ps1 v0.0.8.4 (05/28/2021) - deletes unnecessary residual Chocolatey files to free up disk space
Copyleft 2017-2021 Bill Curran (bcurran3@yahoo.com) - free for personal and commercial use

Choco-Cleaner Summary:
  **  Deleting unnecessary Chocolatey _processed.txt (WTF?) file...
  **  Deleting 16 unnecessary Chocolatey .ignore files...
  **  NO unnecessary Chocolatey .old files to delete.
  **  Deleting 12 unnecessary Chocolatey cache files (C:\Users\TONESO~1\AppData\Local\Temp\chocolatey)...
  **  NO unnecessary Chocolatey cache files (C:\WINDOWS\temp\chocolatey) to delete.
  **  Deleting 25 unnecessary Nuget cache files...
  **  Deleting unnecessary Chocolatey config backup file...
  **  Deleting 1 unnecessary Chocolatey lib-bad package files...
  **  NO unnecessary Chocolatey lib-bkp package files to delete.
  **  NO unnecessary Chocolatey package embedded archive files in toolsDir to delete.
  **  Deleting unnecessary Chocolatey package embedded archives and executables in .nupkg files...
  **  NO unnecessary Chocolatey package embedded Microsoft installers to delete.
  **  Deleting 2 unnecessary Chocolatey package embedded various read me files...
  **  NO unnecessary Chocolatey orphaned shim files to delete.
Choco-Cleaner finished deleting unnecessary Chocolatey files and reclaimed ~ 616,156 KB!
Found Choco-Cleaner.ps1 useful?
Buy me a beer at https://www.paypal.me/bcurran3donations
Become a patron at https://www.patreon.com/bcurran3
</pre>

- All done!