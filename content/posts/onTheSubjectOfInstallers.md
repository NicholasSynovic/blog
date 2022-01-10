---
date: 2022-01-10T13:04:35-06:00
description: "My thoughs on software installers"
summary: "My thoughts on software installers"
title: "On the Subject of Software Installers"
toc: true
show_comments: true
---

> My thoughts on software installers

## Who cares?

Well, you should. You most likely operate one or more computers a day, each running software that at some point had to be installed. Whether this software was bundled with your computer's OS, or if you compiled it from source code, at some point you had to interact with one or more pieces of software to operate your computers. And to be frank, software installers suck.

## An Installer's Purpose 

An installer should:

* Install and register its associated software with the computer's OS
* Change its purpose and become an uninstaller
 
Installers shouldn't:

* Ask me if I want to install extra or addon software
* Get in the way with prompts or checkboxes
* Force me to read EULA's
* Download updates from the internet
* Require me to watch the software install

Now, why this specific list? Because it both describes the bare minimum that an installer **should** do and lists some of my complaints with what it **shouldn't** do but I've experienced.

## One Installer for Many Software

I think we can agree that an installer should install software. But it should only be allowed to install *one specific software and its dependencies*. Too often on Windows do I download and start installing software only to have prompts appear asking if I want to install additional software. Why would I? I came to download a specific piece of software, not any additional software.

This problem isn't limited to Windows alone. I see this happen when I install software with a package manager in Linux. The only difference between the two is that in Linux, I can be as specific or as generic as I want when I install software. So it is purely user error.

Unlike Windows where the developers of the tool went out of their way to write code in the installer to ask me to install extra software. If this software is that important that you have to include it in your installer, integrate it into your software! Make it a required dependency that your software relies on to run.

### Solutions

As I wrote above, if a software utility is integral to your application working, it better be a dependency of the main application. Otherwise, scrap it and think of something else.

If you have to include extra software in your installer, it better serve some purpose for the application that is being installed. If it is fluff, remove it.

### The Business Arguement

With that being said, I understand the business case for including this additional software in an installer. If Company A decides that Company B's software is popular enough and is installed on *n* number of computers, then A can and should approach B about some kind of bundling agreement. This agreement could specify what software A wants B to bundle, and how much money A will compensate B for doing so. As companies are institutions that have to make money to survive, I can see how this is a lucrative deal for both companies as A gets money, and B gets their product into the hands of more users.

However, users suffer due to this agreement. Particularly non-tech savy ones that click next on every checkbox without reading what is being installed or thinking that it is essential that they install the addon software. These users (among others) suffer because if the marketing strategy works, both the desired software from Company A is installed and the undesired Company B software is also installed. Furthermore, with the more software crap that is installed on a system, the more likely that a malicous actor can conduct an attack using one of the pieces of software as an entry point.

## Too Many Options

## Hiding Options
