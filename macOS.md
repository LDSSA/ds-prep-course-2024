# Set-up instructions for MacOS

Welcome to the **MacOS set up**!

Your first step in this journey is to **carefully read** the steps in this tutorial. You'll learn how to set up your computer.

### MacOS Setup

Some of the steps in the following sections will require **'Homebrew'** for MacOS. **'Homebrew'** is a package manager - it helps you installing software. Installing **'Homebrew'** will make it easier to install software that we will use later on.

**Step 1:** Open a **'terminal'** in one of the following ways:

- In Finder <img src='media/finder.png' alt='Finder' width="4%" />, open the `/Applications/Utilities` folder, then double-click **'terminal'**.
- Press <kbd>cmd</kbd> + <kbd>space</kbd> then type **'terminal'** and press <kbd>enter</kbd>.

  The terminal should now be open:

    <img src='media/mac_terminal.png' width="50%" />

**Step 2:** To install **'Homebrew'** for MacOS, copy and paste the following line in the terminal:

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

**Step 2.1:** Sometimes it's necessary to install **'xcode command line utils'**. To do so, execute the following command before installing **'Homebrew'**:

```bash
xcode-select --install
```

You may be prompted to install the **'`Command Line Developers Tools'**. Confirm and once it finishes, continue installing **'Homebrew'** by pressing <kbd>enter</kbd> again.

**Step 3:** Open a terminal and run the following command to update **'Homebrew'**. The verbose option means that **'Homebrew'** will tell you what it's doing - you will see a lot of text output in your terminal:

```bash
brew update --verbose
```

**Step 4:** Now run the following command to install **'Git'**. **'Git'** is a version control software that facilitates collaboration of people working together on the same code and keeps track of the versions as the code changes. You will learn more about **'Git'** in **'Week 02'** of this course.

```bash
brew install git
```

**Step 5:** Now run the following command to install **'Python 3.11'**:

```bash
brew install python@3.11
```

**Step 6:** then run the following command to set the default **'Python 3.11'** version to 3.11:

```bash
brew link python@3.11
```

And you're done! Go back to the main menu and continue with setting up Git and GitHub in [step 3](README.md#3-setup-git-and-gitHub).