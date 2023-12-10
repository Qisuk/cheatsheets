

## SolutionPackager
 The SolutionPackager tool is distributed as part of the NuGet package Microsoft.CrmSdk.CoreTools.

 The SolutionPackager tool is an executable that you can use to conduct the following actions:
* Extract: Extract solution .zip file to a folder
* Pack: Pack a folder into a .zip file
https://learn.microsoft.com/en-us/power-platform/alm/solution-packager-tool

```
pac solution init --publisher-name developer --publisher-prefix dev
pac solution add-reference --path c:\Users\Downloads\SliderComponent
```

```
pac solution pack --zipfile C:\MyProject.zip --folder .\MyProjectUnpacked\.
pac solution unpack --zipfile C:\MyProject.zip --folder .\MyProjectUnpacked\.
```
### Building a package
init a new package
```
pac package init --outputDirectory MyPackage
```
include an existing package
```
pac package add-solution --path ..\MySolution1_1_0_0_2_managed.zip
```
publish
```
dotnet publish
```
will create a .zip file containing everything needed to deploy the package

### deploying a package 
https://learn.microsoft.com/en-us/power-platform/admin/deploy-packages-using-package-deployer-windows-powershell/

## Install developer tools

install the Configuration Manager Tool.
```
pac tool cmt
```

install the Package Deployer Tool.
```
pac tool pd
```

install the Plugin Registration Tool.
```
pac tool prt
```

## power platform CLI

```
pac install latest
pac pcf init --namespace Contoso --name Slider --template field
npm install
pac pcf init --namespace Contoso --name Slider --template field --run-npm-install
npm run build
npm start
pac pcf push --publisher-prefix dev
```

## Tools for Visual Studio


```
pac solution init --publisher-name Contoso --publisher-prefix contoso ‑‑outputDirectory vssolution
pac solution add-reference --path \<path to your Power Apps component framework project\>
msbuild /t:build /restore
```
