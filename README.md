# How to Update Everything Everywhere All One by One
This is a cheat sheet for updating critical web software.

Using outdated application is a high risk vulnerability that has an easy fix. This guide provides easy to follow instructions for different applications to fix security vulnerabilities.

> The goal of this guide is not to update everything to the latest version. The solutions are provided to fix security issues with minimum changes. Whenever this is not possible, a note is added.

## RHEL/CentOS/Oracle Linux
Run below command in terminal (ssh)
```
sudo yum update
```

## Debian/Ubuntu Linux
Run below command in terminal (ssh)
```
sudo apt update && sudo apt upgrade
```

## OpenSUSE/SUSE Linux
Run below command in terminal (ssh)
```
sudo zypper up
```

## NodeJs (npm)
Run below command in your NodeJs project directory.
```
npm audit fix
```

Note that some vulnerabilities cannot be fixed automatically and will require manual intervention or review.
Some fixs can be forced using below command but you need to make sure it doesn't break anything.
```
npm audit fix --force
```

## Python (pip)
You have to update packages one by one. Run below command to get list of outdated packages.
```
pip list --outdated
```
For each package run below command to update it.
```
pip install [package_name] --upgrade
```

## NuGet
From the command line you can update packages in the solution to the latest version available from nuget.org.
```
nuget update YourSolution.sln
```

Note that this will not run any PowerShell scripts in any NuGet packages.

From within Visual Studio you can use the [Package Manager Console](http://docs.nuget.org/docs/reference/package-manager-console-powershell-reference) to also update the packages. This has the benefit that any PowerShell scripts will be run as part of the update where as using NuGet.exe will not run them. The following command will update all packages in every project to the latest version available from nuget.org.
```
Update-Package
```

## PHP (Composer)
Navigate to the root of your application, where your `composer.json` file is and run below command.
```
composer update
```

## Go (golang)
To update all packages in your `GOPATH`, run below command.
```
go get -u all
```

## WordPress
WordPress lets you update with the click of a button.  You can launch the update by clicking the link in the new version banner (if it’s there) or by going to the Dashboard > Updates screen. Once you are on the *“Update WordPress”* page, click the button *“Update Now”* to start the process off. You shouldn’t need to do anything else and, once it’s finished, you will be up-to-date.

## Windows
Run below command on `cmd` to open Windows update screen.
```
control update
```

## References
- [npm-audit](https://docs.npmjs.com/cli/v8/commands/npm-audit)
- [Updating WordPress](https://wordpress.org/support/article/updating-wordpress/)
- [stackoverflow.com](https://stackoverflow.com/a/6882750)
