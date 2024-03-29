# Programs to Install

You should be using a Windows computer. You can definitely use a Mac or a Linux computer (With a distro that can use VS Code), but you will only be able to write code for the robot. You won't be able to use FRC's programs which let you use the robot. You'll have to use one of the team's laptops if you want to turn on the robot and drive it.

## Java

[Download Link](https://adoptopenjdk.net/)

As of the 2023 season, you are supposed to get Java 11. This is not the newest version. Yes, every version of Java is backwards compatible, but sometimes we encounter things that don't support the newest version of Java... somehow...

## FRC Game Tools

[Download Link](https://www.ni.com/en-us/support/downloads/drivers/download.frc-game-tools.html#333285)

This installs a few programs, but it most notably installs Driver Station and RoboRIO Imaging Tool.

There's a button on every robot that turns the power on, but the robot won't actually move until you connect to it with Driver Station and enable the robot.

As a programmer, you will be mostly working with the RoboRIO. The RoboRIO is a computer on the robot where the code you write will be running off of. The RoboRIO Imagine tool lets you update it.

**You don't need the serial key to install it**. It will ask you for a serial key, but if you close that window, you can still use the software indefinitely - winrar style. It will pester you for it, so you should ask the software director if they have it. You can always enter the serial key after completing the installation, so don't feel afraid to close out the serial key popup.

Mac/Linux: If you have only have a Mac as a personal device (or if you're a loser who uses Linux only), don't worry, you can still push code to the robot. However, you **CAN NOT** use your computer at competitions, a Windows laptop **MUST** be used. [QDriverStation](https://github.com/FRC-Utilities/QDriverStation/releases/tag/v21.04) is a workaround for non Windows laptops in order to communicate with the RoboRIO. Setup is rather simple, just install the required file type, and make sure to set up the Xbox Controller driver as well.

## Visual Studio Code

[Download Link](https://code.visualstudio.com/)

VS Code is the IDE officially supported by FRC. It is designed to be used for any programming language if you have the correct extensions.

## Visual Studio Code Extensions

In VS Code, go to the sidebar and go to the extension marketplace. You can search for extensions in the search bar.

- [WPILib](https://marketplace.visualstudio.com/items?itemName=wpilibsuite.vscode-wpilib) - We use classes are not in the vanilla JDK. This extension installs the FRC libraries and it gives us the ability to deploy code to the robot.
- [Java Extension Pack](https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-java-pack) - VS Code is meant for any language, but you need to install the extension for it. This extension gives you syntax highlighting (color codes your code), tells you if your code has any errors, and more.

These are not required, but I like these:

- [Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) - Don't think you're above it.
- A theme of your choice - You should feel warm and fuzzy inside when you code, and the best way to achieve that is with a nice theme. I personally use [One Dark](https://marketplace.visualstudio.com/items?itemName=akamud.vscode-theme-onedark) and use [this](https://marketplace.visualstudio.com/items?itemName=PKief.material-icon-theme) for my icon set
- I uninstalled [Java Test Runner](https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-java-pack) because we, sadly, don't write tests for our robot, so I felt it was just visual clutter.

## Github Desktop

[Download Link](https://desktop.github.com/)

Git is a version control system. You can turn a folder on your computer into something called a "Git Repository". It's like cloud storage (like Google Drive), but made specifically for code and collaboration. Traditionally, Git is used in a terminal, but Github has a very nice program that lets you use Git easily in a GUI.

Git and Github are two different things. Github is to Git like GMail is to emails. Github merely hosts Git on their servers. There are other providers for Git like Gitlab and BitBucket, but we use GitHub because it's the most mainstream and we're not weird.

## Git (Git Bash)

[Download Link](https://git-scm.com/downloads)

Want something a bit more complex than GitHub Desktop? Then Git is just for you my coding friend! Git (like previously mentioned) is a version control system that is used to store/share code. Git Bash allows you to use Git from the command line, giving you a lot more freedom (and frustration) when compared to GitHub Desktop. You can even use Linix/Unix commands and Windows commands.
<br/> 

**Note!-** Both Git and GitHub Desktop (despite it's name) can used in conjunction with most online Git repositories (such as **GitHub**, **GitLab**, **BitBucket**, etc).

## Phoenix Library

[Download Link](https://store.ctr-electronics.com/software/)

Newest version, with the installer.

Cross the Road Electronics sells the Talon and Falcon speed controllers that we use in the robot. This stuff downloads the libraries needed to use them, and a program that lets us configure them.

## Rev Hardware Client

[Download Link](https://docs.revrobotics.com/rev-control-system/managing-the-control-system/rev-hardware-client)

Press the orange button to download it.

## Libraries

[GitHub](https://github.com/Mars1523/FRC-Vendor-Libraries)

This is a page for all the common vendor libraries. We import these whenever we work with a specific piece of hardware, since this is a lot more convenient than managing locally installed versions.
