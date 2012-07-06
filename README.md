# Welcome to Yumitude

Yumitude is an open source project seeking to solve the burden of identifying packages to be installed using different package managers on *nix based systems. 

## Introduction

The goal of the project is to simplify identifying which package name is appropriate for a particular distribution of Linux. Often, whilst attempting to install a particular tool, or project on another Linux OS (or Mac OSX via Homebrew or Fink or Macports etc), it can be mind numbingly painful. Lets fix that. Current package managers like Aptitude, Yum (RPM), Macports etc have different naming conventions for what are often common libraries.

For example:

  * libcurl (Aptitude) <-> curl-devel (Yum)

## Usage

In order to find a package name, curl can be used:

    # From a CentOS machine

    $ curl yumitu.de/libcurl
    curl-devel

Generally:

    curl yumitu.de/PACKAGE_NAME

Yumitude relies on the User-Agent HTTP header to determine which way to translate. I.e. If you request the name of a Debian package from a RedHat linux distribution such as CentOS, you'll get back the appropriate RPM package name. So, if you want to get the package name translation of a different OS, you can adjust the User-Agent header:

    curl -H "User-Agent: <OS_NAME>" yumitu.de/<PACKAGE_NAME>

## Contributing

If you've found a mis-translated package, or if you'd like to extend what we currently have, simply update the relevant YAML file and issue a pull request.

Otherwise, if you want to contribute, issue a pull request!

## Licence

Yumitude is released under the [MIT License](http://www.opensource.org/licenses/MIT):

  * http://www.opensource.org/licenses/MIT