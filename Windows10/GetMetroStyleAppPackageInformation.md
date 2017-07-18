# How To
## Get the Metro style app package information

* Run this in Powershell to list the apps with a specific string in its name:
  ```powershell
  # AppName is the app name or part of the app name to search for
  Get-AppxPackage | findstr "<AppName>"
  ```
* Following details are show for the app:
  ```powershell
  Name              : ...
  Publisher         : ...
  PackageFullName   : ...
  InstallLocation   : ...
  PackageFamilyName : ...
  ```
* For more details, extract the `Name` from the above details and run the following:
  ```powershell
  Get-AppxPackage <Name>

  # Following details will show up
  Name              : ...
  Publisher         : ...
  Architecture      : ...
  ResourceId        : ...
  Version           : ...
  PackageFullName   : ...
  InstallLocation   : ...
  IsFramework       : ...
  PackageFamilyName : ...
  PublisherId       : ...
  IsResourcePackage : ...
  IsBundle          : ...
  IsDevelopmentMode : ...
  ```
* If more than one result comes up search for the appropriate one using `Find` command on the Powershell window.

### Get App ID for the app

* Goto `InstalledLocation` found in the above app package details.
* Open `AppxManifest.xml`
* Look for *Executable=* for the app you want and extract the `Id` value on that node. This `Id` is the app ID that you are looking for.

## References

* [How can I show a list of installed apps (“Metro” only) in Windows 10?](https://superuser.com/questions/1029965/how-can-i-show-a-list-of-installed-apps-metro-only-in-windows-10)
* [Windows 10: Method to open any Windows 10 Apps from command line](https://www.tenforums.com/software-apps/57000-method-open-any-windows-10-apps-command-line.html)