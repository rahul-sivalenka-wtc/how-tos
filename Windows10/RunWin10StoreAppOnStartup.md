# How To

## Run Windows 10 Store app or Metro style app on startup using a batch file

* Find the app's package family name by following the steps in [Get App Package Information](GetMetroStyleAppPackageInformation.md)
  ```powershell
  # Package family name will be in the following form
  Microsoft.SkypeApp_kzf8qxf38zg5c
  ```
* Create a batch file with the following content. (Replace the `PackageFamilyName` with your app)
  ```batch
  @ECHO OFF
  explorer.exe shell:AppsFolder\<PackageFamilyName>!<AppId>
  ```
  
  > Don't forget to suffix the package family name with `!<AppId>` where app ID can be extracted by following the steps in [Get App ID for the app section](GetMetroStyleAppPackageInformation.md#Get-App-ID-for-the-app)
* Open startup folder by running `shell:startup` in the Run command.
* Paste the batch file created there.

### Adding a delay to the app startup

* Add the following after the `@ECHO OFF`
  ```batch
  @ECHO OFF
  REM Here this will wait for 30 sec before executing the next statements
  Powershell /c Sleep 30

  explorer.exe shell:AppsFolder\<PackageFamilyName>!App
  ```

## References

* [Delay program launch using script](https://social.technet.microsoft.com/Forums/windows/en-US/898e0aae-dbef-4327-9c61-7d2f8af3185f/delay-program-launch-using-script?forum=w7itproinstall)
* [Launch Metro style apps using powershell](https://stackoverflow.com/questions/31798580/launch-metro-style-apps-using-powershell)
* [Windows 10: Method to open any Windows 10 Apps from command line](https://www.tenforums.com/software-apps/57000-method-open-any-windows-10-apps-command-line.html)