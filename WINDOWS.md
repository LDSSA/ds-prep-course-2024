# Set-up instructions for Windows 10/11

Welcome to **Windows 10/11 set up** repository!

Your first step in this journey is to **carefully read** the steps in this tutorial. You'll learn how to set up your computer. This section deals with setting up `Windows Subsystem for Linux` (WSL) on Windows 10/11. `Windows Subsystem for Linux (WSL)` enables you to run Linux command line inside Windows.

**Step 1:** Follow **[this guide](guides/Windows_Subsystem_for_Linux_Installation_Guide_for_Windows_10.md)** to setup `WSL` on Windows 10/11.

**Step 2:** Open a terminal (remember **[this](guides/Windows_Subsystem_for_Linux_Installation_Guide_for_Windows_10.md#Opening-the-WSL-terminal)**!!) and run the following command. It will install `git`. `Git` is a version control software that facilitates collaboration of people working together on the same code and keeps track of the versions as the code changes. You will learn more about `git` in Week 02 of this course.

```bash
sudo apt update && sudo apt upgrade && sudo apt install git
```

**Step 3:** Open a terminal (remember **[this](guides/Windows_Subsystem_for_Linux_Installation_Guide_for_Windows_10.md#Opening-the-WSL-terminal)**!!) and check if you already have `python3.11` by usind the command below. If your version is `Python 3.11.x` (`x` = any number), you can skip to step 4, otherwise continue with step 3.1 and 3.2.

```bash
python3.11 --version
```

**Step 3.1:** Run the following commands to set up `Python 3.11` (if you get an error with this command, check [this](troubleshooting.md/#6-when-setting-up-python-38-i-get-an-error)). First, add the `deadsnakes repository` - a place from where you will download `Python 3.11`:

```bash
sudo add-apt-repository ppa:deadsnakes/ppa
```

**Step 3.2:** Run the following commands to install `Python 3.11`:

```bash
sudo apt update && sudo apt install python3.11 -y
```

**Step 4** Run the following command to get `pip` and `venv`. `pip` is a package manager - it will help you easily install software. `venv` is a software for creating virtual environments (we will come back to what this means in the next set up step):

```bash
sudo apt update && sudo apt upgrade && sudo apt install python3-pip python3.11-venv -y
```

And you're done! Go back to the main menu and continue with setting up Git and GitHub in step 3.
