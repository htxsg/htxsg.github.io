---
title: Developer Machine
author: panyong
categories: [news, updates]
tags: featured
---

This article covers the basic setup requirement to get productive when a developer receives his/her machine.


#### Table of Content
{:.no_toc}
* TOC
{:toc}

# Introduction

All cloud team gets a standard issue of either a M1 Mac 16" or M1 Mac 13" developer machine. Getting one's machine up can be a chore, here's a guide on software one need before getting productive.

16" or 13" will be the first question to answer. I already have a 13" Mac, so I'd opted for the 16", it really good to have a bigger screen and not needing to plug into a screen. The 16" is heavy, but it has more ports and a larger battery. Both models as amazing long battery life and the M1 chip doesn't heat up, really comfortable on the lap.

# Software

## Essentials: Xcode, Homebrew, Python & Git
These are the top 3 tools that are essential for development on a Mac.

### Homebrew

1. Download [Xcode](https://developer.apple.com/xcode/). The installation will take a while.

2. We need a package manager. Install [Homebew](https://brew.sh). Let's test out homebrew by installing wget.

Install wget:

```bash
% /opt/homebrew/bin/brew install wget
Running `brew update --preinstall`...
==> Homebrew is run entirely by unpaid volunteers. Please consider donating:
  https://github.com/Homebrew/brew#donations
...
```

Use wget to get webpage from Google:

```console
% /opt/homebrew/Cellar/wget/1.21.3/bin/wget www.google.com
--2022-04-30 11:00:52--  http://www.google.com/
Resolving www.google.com (www.google.com)... 142.251.10.104, 142.251.10.105, 142.251.10.103, ...
Connecting to www.google.com (www.google.com)|142.251.10.104|:80... connected.
HTTP request sent, awaiting response... 200 OK
Length: unspecified [text/html]
Saving to: ‘index.html’

index.html              [ <=>                ]  15.77K  --.-KB/s    in 0.01s   

2022-04-30 11:00:52 (1.37 MB/s) - ‘index.html’ saved [16149]
```
Great. It is all good. Remember to `rm index.html`.

### Python
It is always useful to have python. One can run python in docker or jupyter Notebook, but the most convenient is to have it available in shell. Download and install [Python 3](https://www.python.org/downloads/macos/). After installation, I did a quick verification on where is python installed and checked if I can run `python3` from home directory:


```
% whereis python3 
python3: /usr/bin/python3 /Library/Frameworks/Python.framework/Versions/3.10/share/man/man1/python3.1

% python3    
Python 3.10.4 (v3.10.4:9d38120e33, Mar 23 2022, 17:29:05) [Clang 13.0.0 (clang-1300.0.29.30)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>> 1+1
2
>>> ^D
% 
```


Add Homebrew to PATH to save some typing.

- look for profile file for the default mac's .zsh shell in your home directory:

```
% cd
% ls -ad .z*
.zprofile	.zsh_history	.zsh_sessions
```

- edit .zprofile file to add /opt/homebrew/bin path. I'm a `vi` guy:

```
% vi .zprofile
# Setting PATH for Python 3.10
# The original version is saved in .zprofile.pysave
PATH="/Library/Frameworks/Python.framework/Versions/3.10/bin:/opt/homebrew/bin:${PATH}"
export PATH
```

- re-launch shell and check if path is added:

```
% echo $PATH
/Library/Frameworks/Python.framework/Versions/3.10/bin:/opt/homebrew/bin:/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin
```

### Git
Finally install Git using Homebrew:
```
% brew install git
% git --version
git version 2.32.0 (Apple Git-132)
```

## Software Development Tools for Cloud
Let's install all the software:
1. First stop, download [VS Code](https://code.visualstudio.com/download). 
2. Get [Docker Desktop](https://www.docker.com/get-started/).
3. Install [AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html).
4. Install [Azure CLI](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli-macos):
```
% brew update && brew install azure-cli
% az --version | more
```
5. Install [Terraform](https://www.terraform.io/downloads):
```
% brew install hashicorp/tap/terraform
% terraform -version
Terraform v1.1.9
on darwin_arm64
```


## Collaboration Tools
1. Google Chrome when Safari doesn't work for every site.
2. Microsoft Teams
3. [draw.io](https://github.com/jgraph/drawio-desktop/releases/) is our go-to diagramming tool.

## Software to Up your Developer Game
1. I like to have more than one text editor. My favourite alternative to VSCode is [Sublime](https://www.sublimetext.com), [Atom](https://atom.io) is pretty okay too.

2. [SourceTree](https://www.sourcetreeapp.com) is an essential tool when you get into some kind of code merging hell.

3. [Postman](https://www.postman.com/downloads/) is a great tool when you need to test API calls.

4. As a Hacker Burp Suite from PortSwigger is a must-have. It is also really great for troubelshooting. Download the free [Community Edition](https://portswigger.net/burp/communitydownload).

5. [NPM and NodeJS](https://nodejs.org/en/download/) to build Javascript frontend and backend solutions.

## Other Hacks

### Use the developer tools in the Develop menu in Safari on Mac
If you don’t see the **Develop** menu in the menu bar, choose Safari > Preferences, click Advanced, then select “Show Develop menu in menu bar.”. The checkbox was right at the bottom at the point of writing.

