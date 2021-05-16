# Cake.ActiveDirectory

Cake Addin for working with Active Directory.

## Give a Star! :star:

If you like or are using this project please give it a star. Thanks!

## Information

| | Stable | Pre-release |
|---|---|---|
|GitHub Release|-|[![GitHub release](https://img.shields.io/github/release/Cake.ActiveDirectory/Cake.ActiveDirectory.svg)](https://github.com/cake-contrib/Cake.ActiveDirectory/releases/latest)|
|NuGet|[![NuGet](https://img.shields.io/nuget/v/Cake.ActiveDirectory.svg)](https://www.nuget.org/packages/Cake.ActiveDirectory)
|[![NuGet](https://img.shields.io/nuget/vpre/Cake.ActiveDirectory.svg)](https://www.nuget.org/packages/Cake.ActiveDirectory)|

## Quick Links

- [Documentation](https://cakebuild.net/extensions/cake-activedirectory/)

## Build

To build this package we are using Cake.

On Windows PowerShell run:

```powershell
./build
```

## About

This Addin only contains the functionality that we needed.  We are more than happy to accept pull requests that will grow this library.  It uses the [LandPy.ActiveDirectory](https://github.com/landpy/ActiveDirectoryLibrary) library for all Active Directory interaction.

## Usage

### Adding to your cake file

```
//Beta version
#addin nuget:https://www.myget.org/F/beta-builds/api/v2?package=Cake.ActiveDirectory 

// Release version
#addin nuget:?package=Cake.ActiveDirectory 
```

### Creating a user

```
CreateUser("cake-user", "cake-group", new UserSettings { 
    LoginName = "domainAdmin", 
    Password = "adminPassword", 
    DomainName = "Cake.net"});
```

### Updating a user

```
UpdateUser("employeeId", "1234", new UserSettings { 
    LoginName = "domainAdmin", 
    Password = "adminPassword", 
    DomainName = "Cake.net",
    Email = "test@cake-yeah.com" });
```

### Getting a user's UPN from their email address.

```
var upn = FindUserPrincipalNameByProperty("proxyAddresses", "jdoe@example.com", new UserSettings { 
            LoginName = "domainAdmin", 
            Password = "adminPassword", 
            DomainName = "Cake.net" });
```

## Discussion

For questions and to discuss ideas & feature requests, use the [GitHub discussions on the Cake GitHub repository](https://github.com/cake-build/cake/discussions), under the [Extension Q&A](https://github.com/cake-build/cake/discussions/categories/extension-q-a) category.

[![Join in the discussion on the Cake repository](https://img.shields.io/badge/GitHub-Discussions-green?logo=github)](https://github.com/cake-build/cake/discussions)

## Release History

Click on the [Releases](https://github.com/cake-contrib/Cake.ActiveDirectory/releases) tab on GitHub.

---

_Copyright &copy; 2017-2021 Cake Contributors - Provided under the [MIT License](LICENSE)._
