# SeemlessUpdater
A seamless updater for dotnet core applications.

# Goal
- The update is assumed to be light
- The updater does not contain any UI dependencies
- The updater should validate the update against its checksum
- The updater should fallback to the previous version if the update failed (the application does not run as expected)
- The updater should preserve any parameters passed to the initial program (when running and updating)
- The application should be able to run with the updater disabled

## File content
```xml
<--! https://raw.githubusercontent.com/cadesalaberry/SeemlessUpdater/main/example/Manifest.xml -->
<?xml version="1.0" encoding="UTF-8"?>
<update>
    <version>1.2.0.0</version>
    <zip-url>https://raw.githubusercontent.com/cadesalaberry/SeemlessUpdater/main/example/ExampleUpdate-1.2.0.0.zip</zip-url>
    <changelog>https://raw.githubusercontent.com/cadesalaberry/SeemlessUpdater/main/example/CHANGELOG.md</changelog>
    <mandatory>false</mandatory>
    <zip-checksum algorithm="sha256">c01b39c7a35ccc3b081a3e83d2c71fa9a767ebfeb45c69f08e17dfe3ef375a7b</zip-checksum>
</update>
```

## File system structure
```
C:\Users\[YourUsername]\AppData\Local\[NameOfYourApp]\
.
|_ [NameOfYourApp]Bootstrap.exe
|_ CurrentVersion.xml
|_ versions\
  |_ 2021.04.17-11_32_45.zip
  |_ 2021.04.17-11_32_45\
    |_ [NameOfYourApp]Bootstrap.exe
    |_ [NameOfYourApp].exe
```
