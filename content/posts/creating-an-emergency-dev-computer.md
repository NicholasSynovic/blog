---
date: 2022-03-14T15:27:53-05:00
description: "An attempt at creating an emergency dev environment that I can utilize anywhere"
draft: false
show_comments: true
summary: "An attempt at creating an emergency dev environment that I can utilize anywhere"
title: "Creating an Emergency Computer"
type: "post"
toc: true
---

## I Have a Problem

I like to develop. Like a lot. To the point where when I go and relax, I
typically read books on the subject, watch videos and lectures about code, and
so forth. I realized this while I was on my Spring Break in Miami, drunk at a
bar, wishing that I wanted to code in the morning. But then I remembered that I
purposefully left my computer at home to avoid coding, got sad, downed my drink,
and then I was happy once again.

But now that I'm home, I realized that I can actually resolve this problem
permanently. And to do so, I'm going to create a development environment that
I will always have on me.

## Here's the Plan

I'm going to use some of my phone's storage space to hold an Ubuntu development
environment. And as a proof of concept, the following languages
will be availible for me to develop with:

* Python
* Java
* Node JS

Truthfully, I don't expect to use this development enviornment for anything
serious. But that's why I'm calling this an *emergency* development environment.

### Requirements

If you intend to follow along for this project, you will need:

* An Android device with an ARM x64 CPU
* [F-Droid](https://f-droid.org/)
* [Termux (installed via F-Droid)](https://f-droid.org/en/packages/com.termux/)
* [Andronix (insalled via the Google Play Store)](https://play.google.com/store/apps/details?id=studio.com.techriz.andronix&hl=en_US&gl=US)

If you don't want to install Andronix, you can download my setup script here.

I will be working through the setup script in this article line by line in this
article.

## Actually Doing the Work

### Step 0: Why an ARM x64 CPU?

While other CPU architectures may work for this project, this particular
architecture is similar to that of the Raspberry Pi's. Since there are many
tutorials on how to compile different pieces of software for the Raspberry Pi,
we can leverage the same information to compile software on our Android device.

### Step 1: Install F-Droid on your Android Phone

I recommend reading the about page and understanding what this app store is
before continuing on.

### Step 2: Install Termux via F-Droid

Download and install the Termux terminal emulator to your device via the F-Droid
app store.

### Step 3: Configuring Termux

Run the following commands in this order:

0. `apt update`
1. `apt upgrade -y`
2. `apt autoremove --purge -y`

These commands update Termux's software sources, upgrade the already installed
software, and remove any uneeded dependencies as well as their configuration
files (if any).

### Step 4: Install Andronix via the Google Play Store

Should it not be availible, here is their [GitHub page](https://github.com/AndronixApp).

### Step 5: Install Ubuntu via Andronix and Termux

The Andronix team is a group that has released
[open source scripts](https://github.com/AndronixApp/AndronixOrigin/tree/master/Installer)
to install several different operating systems on top of Android OS via
[PRoots](https://wiki.termux.com/wiki/PRoot). I highly recommend checking out
these links to support both the Andronix and Termux teams respectively. Without
their work this project couldn't have happened.

To install Ubuntu via Andronix, open the Andronix app and:

0. Tap the Ubuntu icon
1. Tap *Proceed*
2. Tap *20.04*
3. Tap *Install*
4. Tap *Desktop Environment*. **NOTE**: This tutorial doesn't go over how to use the
included desktop environment. However, this version contains several
dependencies that will make your life easier should you be following along.
5. Tap *XFCE*
6. Tap *Open Termux*
7. Paste the copied text into the Termux command line and tap enter to kickoff
the process of installing Ubuntu 20.04 with the XFCE desktop environment.
**NOTE**: This isn't a headless install. You will have to monitor your phone and
answer propmpts as they appear. I can't provide futher information about this as
it is context sensitive to your timezone, keyboard layout, etc.

### Step 6: Setup Ubuntu 20.04

Run the following commands in this order:

0. `apt update`
1. `apt upgrade -y`
2. `apt autoremove --purge -y`

These commands update Ubuntu's software sources, upgrade the already installed
software, and remove any uneeded dependencies as well as their configuration
files (if any).

### Step 7: Actually Install Development Software

The following commands install the software that I want in my environment.
Obviously, adjust the commands below to match your needs:

0. `apt install git vim openjdk-17-jre openjdk-17-jdk -y`
1. `apt-get install build-essential gdb pkg-config libbz2-dev libffi-dev libgdbm-dev libgdbm-compat-dev liblzma-dev libncurses5-dev libreadline6-dev libsqlite3-dev libssl-dev lzma lzma-dev tk-dev uuid-dev zlib1g-dev -y`
2. `git clone https://github.com/python/cpython python && cd python && ./configure --enable-optimizations -j 8 && cd .. && rm -r python`
**NOTE**: The `-j` flag is the number of cores to use to compile the software.
You can find out the maximum number of cores that you can use by dividing
the output of `nproc` by 2
