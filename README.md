# Software Maintenance: Installing, Updating, and Uninstalling Software on Linux and Windows Machines

---

## Introduction

This brief exercise teaches you how to perform basic software maintenance on **Linux** and **Windows** machines. This includes **installing** new software for the first time, **updating** existing software to the newest version, and **uninstalling** software that's no longer needed. All of these tasks are very common in the world of IT and IT support.

---

## What You'll Do

There are three key learning objectives for this exercise:

* **Install:** You will install the **Mozilla Firefox** web browser. There's currently no version of Firefox on the machine, so it will be a fresh installation.
* **Update:** There is a preinstalled old version of the **VLC Media Player**. You'll update VLC to the newest version.
* **Uninstall:** You'll uninstall the **GIMP** photo-editing tool from the machine, removing it entirely.

---

## Verify Installed Software

The first step is to verify the initial software setup, or "configuration," of programs on your machines. It's important to know how to check for this information.

You'll verify that **Mozilla Firefox** isn't installed on your machine, and that both **GIMP** and **VLC Media Player** (version 3.0.8, in this example) are installed. These can be any software in your case.

### Windows OS

1.  Click the **Search icon** in the bottom-left of the taskbar and start typing "Apps & Features" to search.
2.  Click **"Apps & Features"** (as shown below) or right-click on the **Start icon**, and click on **"Apps & Features"** at the top of the menu.

<br />
<img src="https://cdn-images-1.medium.com/max/1200/1*aBXvhEPVza3TiRMMV6l77Q.png" width="600" alt="screenshot of interface"/>
<br />

  
This will bring up the Apps & Features window, which shows a list of every program that's installed on the computer.*

<br />
<img src="https://cdn-images-1.medium.com/max/1200/1*PaS65AC34HgvkmuiPBbZuA.png" width="600" alt="screenshot of interface"/>
<br />


### Linux OS

You can check if a program is installed by using the command `dpkg -s` followed by the unique package name for that program. The `dpkg` stands for Debian package, indicating that we are using a Debian-based operating system (OS) like Ubuntu. The `-s` flag in the command stands for "search" — it allows you to search for a program on your machine and check if it's installed.

* For example, we know that Firefox isn't currently installed, but GIMP is. So if you run:

    ```bash
    dpkg -s firefox-esr
    ```
    You'll get an output similar to the below, indicating Firefox isn't installed:

    ```
    dpkg-query: package 'firefox-esr' is not installed and no information is available
    Use dpkg --info (= dpkg-deb --info) to examine archive files.
    ```

* Running `dpkg -s vlc` shows you that VLC is installed, but also that the version is out-of-date (Version 2.2.7 is installed, but the newest version is at least 3.0.17).

    ```bash
    dpkg -s vlc
    ```
    ```
    Package: vlc
    Status: install ok installed
    Priority: optional
    Section: video
    Installed-Size: 4667
    Maintainer: Debian Multimedia Maintainers <pkg-multimedia-maintainers@lists.alioth.debian.org>
    Architecture: amd64
    Version: 2.2.7-1~deb8u1
    ```

---

## Installing Software: Mozilla Firefox

### Linux OS

Let's install the **Mozilla Firefox** web browser on a Linux machine. It's noteworthy that lots of common programs, including Firefox, are set up in **repositories** that most Linux distributions (distros) are aware of by default.

You can view repositories as servers that act as central storage locations for packages. This makes installing programs easy, allowing you to skip manual downloads and program installation.

1.  Running the command below ensures that the repositories are up-to-date and all dependencies are fixed or in place:

    ```bash
    sudo apt-get update -y
    ```
    ```
    Hit:1 [http://deb.debian.org/debian](http://deb.debian.org/debian) buster InRelease
    Hit:2 [http://deb.debian.org/debian](http://deb.debian.org/debian) buster-updates InRelease
    Hit:3 [http://security.debian.org/debian-security](http://security.debian.org/debian-security) buster/updates InRelease
    Reading package lists... Done
    ```
    * **`sudo`** means "Super user do" — it's a way of assuming root user power, which permits you to carry out sensitive operations like installing and uninstalling software.
    * **`apt-get`** is a command-line tool that retrieves packages and their dependencies.
    * **`-y`** means "yes" — a way to bypass the prompt to confirm an operation.

2.  Since the above command updates the repository, let's install Firefox next by running the command below in the terminal:

    ```bash
    sudo apt-get install -y firefox-esr
    ```
    You'll see that the status says "installed," which means that the process was successfully completed!

### Windows OS

1.  The first step to installing the **Mozilla Firefox** browser is to download the Windows installer from the Firefox website. To do this, open a Chrome browser and navigate to this URL:
    [https://www.mozilla.org/en-US/firefox/new/](https://www.mozilla.org/en-US/firefox/new/)
2.  From this page, click the **"Download"** link to download the installer.

    ![Download Firefox Installer](https://via.placeholder.com/600x300?text=Mozilla+Firefox+Download+Page)

3.  Once the download finishes, check for the downloaded file in the **"Download"** directory on your computer and double-click on it. This launches the installer and starts the installation process.
4.  Click **"Yes"** if Windows asks if you wish to install it, and the installer should open and begin.
5.  Click **"Next"** through any options that appear during the installation process. Wait for this process to finish, and Mozilla will be installed. A shortcut to Firefox will be added to the desktop, and you can double-click it to open your newly installed browser.

**Congratulations!** You've completed the installation of software using Windows and Linux. Next, you'll configure updates for software already installed on your machine.

---

## Updating Software: VLC Media Player

### Linux OS

**VLC Media Player** is already installed on your computer, but the version that's installed is out-of-date. You'll fix that by updating it to the newest version.

1.  To do that, force an update of the package manager using this command:

    ```bash
    sudo apt-get install -fy
    ```
    This kicks off the update process.

2.  When the process is finished, enter the command below to verify the installation:

    ```bash
    dpkg -s vlc
    ```
    You'll see here that VLC has been updated to a newer version (3.0.17 was the newest at the time this screenshot was taken). Your version should be at least 3.0.17.

### Windows OS

With an old version of **VLC Media Player** already installed on the Windows computer, we will learn how to update it in Windows.

1.  First, you need to get an installer for the new version from VLC's website. Open the link below to download the installer:
    [https://www.videolan.org/vlc/download-windows.html](https://www.videolan.org/vlc/download-windows.html)
2.  Click on the drop-down menu beside **"Download VLC"** and select **"Installer for 64bit version"** and wait for the installer to finish downloading.

    ![Download VLC Installer for Windows](https://via.placeholder.com/600x300?text=VLC+Download+Page)

3.  Once done, click on the installer to open it from the **"Download"** directory.
4.  Once the installer opens, choose whichever language you're comfortable with, then click **"Next"** to begin the process.
5.  Choose **"Upgrade VLC using previous settings (recommended)"** and then click **"Next"**. A progress bar appears and the upgrade process begins.

    ![VLC Upgrade Options](https://via.placeholder.com/600x300?text=VLC+Upgrade+Prompt)

6.  When the process is finished, a confirmation message will appear. Uncheck the option to run VLC, then click **"Finish"** to close the installer.
7.  Reopen the **"Apps & Features"** window and you'll see that VLC is now at the latest version.

---

## Uninstalling Software: GIMP

### Linux OS

One last aspect of software management that we will look into is uninstalling programs. When it's no longer necessary to have a specific program installed on your computer, it's usually a good idea to uninstall it to clear up space. Now, you'll uninstall the **GIMP** photo-editing software, removing it from the computer completely.

GIMP, like any other program on your computer, can be installed and uninstalled using the `apt-get` commands that you used to install Firefox.

1.  To uninstall GIMP, a very similar command is used:

    ```bash
    sudo apt-get remove -y gimp
    ```
    This command will kick off the process of uninstalling GIMP from your instance, and eventually GIMP will be uninstalled.

2.  You can verify that the process was successful by running the same command we used to verify its installation:

    ```bash
    dpkg -s gimp
    ```
    You'll receive the following message. Note that this message shows that GIMP has been uninstalled.

    ```
    dpkg-query: package 'gimp' is not installed and no information is available
    Use dpkg --info (= dpkg-deb --info) to examine archive files.
    ```

### Windows OS

Uninstalling a program on Windows is a straightforward process.

1.  Navigate back to **"Apps & Features"** and right-click on the program you want to remove (i.e., GIMP). A single-item dropdown menu should appear:

    ![Uninstall GIMP on Windows](https://via.placeholder.com/600x300?text=Uninstall+GIMP+Option)

2.  Click on the **"Uninstall"** option in the dropdown. A confirmation menu will appear, asking if you're sure you want to proceed.
3.  Click **"Yes"** and the uninstallation process will begin.
4.  When this process finishes, a confirmation menu will appear. Clicking **"OK"** on that menu will close it, and GIMP should no longer appear on the list of installed programs. This completes the uninstallation process.

---

## Summary

**Congratulations!** You've learned an important skill for maintaining software. We successfully installed, updated, and even uninstalled a program that was no longer relevant and taking up precious space on your storage drive. We carried out these tasks on both Windows and Linux operating systems.

Thank you for reading, and see you in the next exercise!
