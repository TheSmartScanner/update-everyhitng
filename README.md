# How to Update Everything Everywhere All One by One
This is a cheat sheet for updating critical web software.

Using an outdated application is a high-risk vulnerability that has an easy fix. This guide provides easy-to-follow instructions for different applications to fix security vulnerabilities.

> ⚠️ The goal of this guide is to eliminate vulnerabilities by updating applications. Sometimes updates can break things or lead to unexpected behaviors. It is up to you to perform enough checking and testing before using commands in this cheat sheet in the production environment.

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
Run the below command in your NodeJs project directory.
```
npm audit fix
```

Note that some vulnerabilities cannot be fixed automatically and will require manual intervention or review.
Some fixes can be forced using the below command but please make sure it doesn't break anything in your project.
```
npm audit fix --force
```

## Python (pip)
You have to update packages one by one. Run the below command to get a list of outdated packages.
```
pip list --outdated
```
For each package run the below command to update it.
```
pip install [package_name] --upgrade
```

## NuGet
From the command line, you can update packages in the solution to the latest version available from nuget.org.
```
nuget update YourSolution.sln
```

Note that this will not run any PowerShell scripts in any NuGet packages.

From within Visual Studio, you can use the [Package Manager Console](http://docs.nuget.org/docs/reference/package-manager-console-powershell-reference) to also update the packages. This has the benefit that any PowerShell scripts will be run as part of the update whereas using NuGet.exe will not run them. The following command will update all packages in every project to the latest version available from nuget.org.
```
Update-Package
```

## PHP (Composer)
Navigate to the root of your application, where your `composer.json` file is, and run the below command.
```
php composer.phar update
```
In Windows:
```
composer update
```

## Go (golang)
To update all packages in your `GOPATH`, run the below command.
```
go get -u all
```

## Ruby (gem)
To update all gems:
```
gem update
```
RubyGems keeps old versions of gems. Run cleanup to remove old gems after an update.
```
gem cleanup
```

## Maven (mvn)
Run the below command to force an update of dependencies.
```
mvn clean install -U
```

## Rust (cargo)
For updating all dependencies of your Rust project, you need to install a third-party crate. Install `cargo-update`:
```
cargo install cargo-update
```
Then run the below command to check for newer versions and update all installed packages.
```
cargo install-update -a
```

## WordPress
WordPress lets you update with the click of a button.  You can launch the update by clicking the link in the new version banner (if it’s there) or by going to the Dashboard > Updates screen. Once you are on the *“Update WordPress”* page, click the button *“Update Now”* to start the process off. You shouldn’t need to do anything else and, once it’s finished, you will be up-to-date.

## Windows
Run the below command on `cmd` to open the Windows update screen.
```
control update
```

## References
- [npm-audit](https://docs.npmjs.com/cli/v8/commands/npm-audit)
- [Updating WordPress](https://wordpress.org/support/article/updating-wordpress/)
- [stackoverflow.com](https://stackoverflow.com/a/6882750)
- [stackoverflow.com](https://stackoverflow.com/a/10383783)
- [stackoverflow.com](https://stackoverflow.com/a/40982333)
