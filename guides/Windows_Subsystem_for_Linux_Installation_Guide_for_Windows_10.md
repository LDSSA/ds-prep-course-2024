# Windows Subsystem for Linux Installation Guide for Windows 10

## 1. Make sure that Windows is up to date

<span id="step-1_1" style="color: black;">&nbsp; 1.</span> Type `updates` in your **'Windows search bar'** to open the **'Windows search filter'**:

![alt text](assets/windows_search_bar.png)

2. Click **'Check for Updates'** in the **'Windows search filter'**:

![alt text](assets/windows_check_for_updates.png)

3. Download and install any updates that appear in the **'Windows Update'** menu (shown below):

<img src="assets/windows_update.png" alt="alt text" width="782" height="auto" />

After you're done installing those updates, please check which **'OS build'** of Windows 10 you are running using the following steps:

4. Type `about` in your **'Windows search bar'** to open the **'Windows search filter'**.

1. Click **'About your PC (System settings)'**:

![alt text](assets/windows_about_your_pc.png)

6. Check **'OS build'** under **'Windows specifications'**:

![alt text](assets/windows_specifications.png)

7. If your **'OS build'** number is at least `19041.x` proceed to [step 2. Install the Windows Subsystem for Linux](#2-install-the-windows-subsystem-for-linux).
    > The 'x' means any number

8. If your **'OS build'** number is smaller than `19041.x`, then please keep coming back to **'Windows Update'** (previous **[step 1.](#step-1_1)**) and installing updates until you have at least **'OS build'** `19041.x`. Then you may proceed with this guide.

> 📝 **Note:** If you have problems checking your system's **'OS build'**, see [Which version of Windows operating system am I running?](https://support.microsoft.com/en-us/windows/which-version-of-windows-operating-system-am-i-running-628bec99-476a-2c13-5296-9dd081cdd808) for more information.

## 2. Install the Windows Subsystem for Linux

Before installing any **'GNU/Linux'** or simply **'Linux'** distribution ([as you wish](https://en.wikipedia.org/wiki/GNU/Linux_naming_controversy) [^1]) using **'WSL'**, you must ensure that both **'Windows Subsystem for Linux'** and **'Virtual Machine Platform'** optional features are enabled.  
Following, you have two possible ways of doing this (approaches 1 and 2). Use the one you find more convenient.

> For additional information about **'WSL'** check [learn.microsoft.com](https://learn.microsoft.com/en-us/windows/wsl/about) 

### Approach 1: Using the Windows interface

1. Type `turn` in your **'Windows search bar'** to open the **'Windows search filter'**.

2. Click **'Turn Windows features on or off'** in the **'Windows search filter'**:

![alt text](assets/windows_turn_windows_features_on_or_off.png)

3. In the **'Windows Features'** menu, activate the required checkboxes, indicated below:

![alt text](assets/windows_features.png)

4. Click <kbd>OK</kbd> to finish.

5. Restart your computer if asked to.

### Approach 2: Using the Windows PowerShell

<a id="step-2_2_1" style="color: black;">&nbsp; 1.</a> Open **'PowerShell'** as Administrator by typing `powershell` in your **'Windows search bar'**, and then clicking **'Run as Administrator'** in the **'Windows Search filter'** under **'Windows PowerShell (App)'**

![alt text](assets/windows_powershell.png)

2. Paste the following command in **'PowerShell'**:

```powershell
Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux,VirtualMachinePlatform
```

![alt text](assets/powershell_turn_on_wsl_and_virtualization.png)

3. Run it by pressing <kbd>enter</kbd>.

4. Restart your computer if asked to.

## 3. Install Ubuntu

Open this link to the [Microsoft Store](https://apps.microsoft.com/detail/9PN20MSR04DW?hl=en-gb&gl=GB) and click **'Download'** to install **'Ubuntu 22.04.x'**.

## 4. Launch Ubuntu

1. Complete the initialization of your newly installed **'Ubuntu'**, launch a new instance. You can either do this by:

- clicking the **'Open'** or **'Launch'** button in the **'Microsoft Store'** page after the download is finished:

  <img src="assets/ubuntu_open_microsoft_store.png" alt="alt text" width="300" height="auto" />

- or typing `ubuntu` in the **'Windows search bar'** and clicking **'Ubuntu 22.04.X LTS'** in the **'Windows search filter'**:

![!\[alt text\](assets/open_ubuntu.png)](assets/windows_search_bar_ubuntu.png)

2. The first time the newly installed **'Ubuntu'** runs, a **'console'** window will open.

      - If you get this error:

        ![alt text](assets/ubuntu_instalation_error.png)

        Go to [Download the Linux kernel update package](https://learn.microsoft.com/en-us/windows/wsl/install-manual#step-4---download-the-linux-kernel-update-package), download the **'WSL2 Linux kernel update package for x64 machines'** under **'1. Download the latest package:'** and install it.  
        Then, go back to the **'console'** and press any key to continue. If necessary, launch **'Ubuntu'** again using one of the methods described in step 1.

      - If you don't get the previous error, you're good to go.

You'll now be asked to wait for a minute or two for the installation to complete.

> During this final stage of installation, **'Ubuntu'**'s files are de-compressed and stored on your PC, ready for use. This may take around a minute or more depending on the performance of your PC's storage devices. This initial installation phase is only required on the first launch. All future launches should take less than a second.

## 5. Setting up a new Linux user account

Once the installation is complete, you will be prompted to create a new **'user account'** (and its **'password'**).

![alt text](assets/UbuntuInstall.png)

This user account is for the normal non-admin user that you'll be logged-in by default when launching **'Ubuntu'**.

> You can choose any **'username'** and **'password'** you wish. They have no bearing on your Windows **'username'**. The only restriction is that the **username** should be in **lowercase**. Beware that when you type passwords in the terminal, you will not see what you are typing. This is a normal behavior in Linux. Just type the **'password'** and hit <kbd>Enter</kbd>.

When you open a new **'Ubuntu'** instance, you won't be prompted for your password, but if you elevate a process using `sudo`, you will need to enter your **'password'**, so make sure you choose a password you can easily remember! On **'Ubuntu'**, every user can do admin tasks such as installing software, but they have to use the magic `sudo` word and input the password. This tells **'Ubuntu'** that you will be acting as admin in the next moments.

> ⚠️ **Important:** Do not forget this **'password'** (along with the associated **'username'**), as you'll not be able to see it again. It is your access card to perform operating system actions that require administrator privileges such as installation of some necessary features to work through the course.

## 6. Checking and setting defaults

**'Ubuntu 22.04'** runs under WSL version 2 (**'WSL 2'**). Typically, **'Windows'** and **'Ubuntu'** take care of the configuration details for you, but still, **it's recommended to check them anyway**, following these steps:

> ⚠️ This is particularly important if you have **previous versions** of WSL/Ubuntu installed on your computer.

1. Close the **'Ubuntu'** console

2. Open the **'PowerShell'** (if it's not already opened), and run the command:

   ```powershell
   wsl --status
   ```

    > 📝 **Note:** To open the **'PowerShell'** check [step 1.](#step-2_2_1) under _Approach 2: Using the Windows PowerShell_.

   You should get an output similar to:

   ![alt text](assets/windows_wsl--status.png)


3. Check the first line of the output

   - If `Default Distribution` is `Ubuntu 22.04` move on to the next step (4.)

   - If it's not, run the following command:

     ```powershell
     wsl --set-default Ubuntu-22.04
     ```

4. Check the second line of the output

   - If `Default Version` is `2` you're good to go

   - If it's not, run the following command:

     ```powershell
     wsl --set-default-version 2
     ```

> This procedure will ensure that Windows always runs the appropriated versions of the enabled and installed features.  
> For additional information about **'WSL'** basic commands visit [learn.microsoft.com](https://learn.microsoft.com/en-us/windows/wsl/basic-commands)

> 📝 Informative: If you have more than one OS feature installed, you can run the following command to get the full scope of your system's current features and state:
>
> ```powershell
> wsl -l -v
> ```

## 7. Opening the WSL terminal

> ⚠️ **Important**: From now on, every time we ask you to open a terminal, this is what you need to do. We'll refer to it just as **'terminal'** instead of 'WSL terminal' or 'Ubuntu terminal'.

1. Whenever you want to use **'WSL'**, just type **'Ubuntu'** in your **'Windows search bar'** and open it in the **'Windows search filter'** (as previously stated):

![alt text](assets/windows_search_bar_ubuntu.png)

2. Then a **'terminal'** window will open that allows you to interact with **'Ubuntu'**.

![alt text](assets/ubuntu_projects_folder.png)

## 8. Enable copy and paste keyboard shortcuts

By default, the **'terminal'** does not allow the usual shortcuts for copying and pasting - you have to enable them first. In the upper left corner of the **'terminal'**, click the orange square, and then click **'Properties'**:

![alt text](assets/ubuntu_properties_option.png)

Then under the **'Options'** tab, in the **'Edit Options'** section, make sure that **'Use Ctrl+Shift+C/V as Copy/Paste'** in enabled and click <kbd>OK</kbd>:

![alt text](assets/ubuntu_copy_paste_option.png)

## 9. Update & upgrade Ubuntu's software packages

Most Linux distributions ship with an empty/minimal software package catalog. We strongly recommend regularly updating your package catalog, and upgrading your installed packages using the appropriate package manager. On **'Ubuntu'**, you use the `apt` package manager. The following command will check for software updates and install them:

```bash
sudo apt update && sudo apt upgrade
```

> Windows does not automatically update or upgrade your Linux distribution since this is a task that its users usually prefer to control themselves.

## 10. How to open Windows File Explorer to manipulate files inside WSL

If you’d like to use **'Windows Explorer'** to manipulate the files in **'WSL'**, just type this in the **'terminal'**.(Don't forget to include the **dot**, which means "`current directory`"):

```console
explorer.exe .
```

The **'Windows Explorer'** should pop up:

![alt text](assets/windows_explorer.png)

If you wish, you can also access your user folder directly from the **'Windows Explorer address bar'** using this path: `\\wsl.localhost\Ubuntu-22.04\home\<YOUR USERNAME>`. This is exactly the same as calling the **'Windows Explorer'** from within your **'Ubuntu user folder'** with the `.` option.

Keep in mind that you should manipulate files and create directories inside your `Ubuntu-22.04/home/<YOUR USERNAME>` folder.

## 11. Final thoughts

You're all set with **'WSL'**! Never imagined yourself using the wonderful Linux operating system? Don't worry too much about it. First because the LDSA team will be with you all the way, and second, well... Microsoft didn't also, but eventually things change... 😉

> _[Microsoft's CEO, Jun 2001](https://www.theregister.com/2001/06/02/ballmer_linux_is_a_cancer/)_ [^2]:
>
> <img src="assets/article_ballmer_statement_about_Linux_2001.png" alt="alt text" width="650" height="auto" />

> _[Microsoft (19 contributors), Nov 2023](https://learn.microsoft.com/en-us/windows/wsl/about#microsoft-loves-linux)_ [^3]:
>
> ![alt text](assets/article_microsoft_loves_linux_2023.png)

That's it! Time to go back to the initial setup for Windows and continue with [step 2](../WINDOWS.md#step-2) of _Set-up instructions for Windows 10/11_.

### References

[^1]: Various contributors - "**_[GNU/Linux naming controversy](https://en.wikipedia.org/wiki/GNU/Linux_naming_controversy)_**". [Wikipedia](https://www.wikipedia.org/), [2024].  
[^2]: Thomas C Greene - "**_[Ballmer: 'Linux is a cancer'](https://www.theregister.com/2001/06/02/ballmer_linux_is_a_cancer/)_**". [The Register](https://www.theregister.com/), (2001).
[^3]: Various contributors (19) - "**_[What is the Windows Subsystem for Linux?](https://learn.microsoft.com/en-us/windows/wsl/about)_**". [learn.microsoft.com](https://learn.microsoft.com/), (2023).
