# PowerShellNotes

A simple repository for recording some of the tricks/tips/tweaks I have learned regarding Powershell.

=============================================
Setting up a more modern terminal on Windows
=============================================

Windows *[Docs](https://docs.microsoft.com/en-us/windows/terminal/tutorials/powerline-setup)* for this process. 

1. Download the Windows Terminal from the Microsoft Store. (Alternatively you can download the github release, however if you choose to do so updates wil have tobe done manually).
2. We will need a Powerline compatible font. (The tutorial I followed used Cascadia Code).
3. After downloading, navigate to your Windows Fonts folder on the C: drive.
4. Copy the PL fonts into the Fonts folder (or right-click and select install).
5. Run Powershell as administrator.
6. type:
```
echo $profile
```
This will show you where your profile should be.  

7. Copy the path up to this point:
```
C:\Users\username\Documents\WindowsPowerShell\
```
8. Type 'start' and then paste the file path.
9. Check to see if a profile exists already. If it does simply open it with:
```
notepad $profile
```
10. Paste in the following three lines of code into notepad:
```
Import-Module posh-git
Import-Module oh-my-posh
Set-Theme Paradox
```
11. You may get an error about how running scripts is disabled. Make sure you are running Powershell in Administrator mode.
12. The easiest way to bypass this error (with serious security concerns) is to simply type:
```
Set-ExecutionPolicy Unrestricted
```
13. Alternatively, look up how to run signed powershell scripts.
14. If you are getting missing character boxes in your powershell, then you need to change the font in your settings, under 'fontFace'.
15. Change the fontFace to Cascadia Code PL (the PowerLine fontface that we are using as part of this tutorial).
16. (You can use other fonts if you want but be aware that depending on the font, other maintenance steps may be required).

*When configuring your powershell you need to open the Settings.JSON from the Windows Terminal (Click the little drop dowm). Add two entries for fontFace and fontSize listing your newly add PL font and the size of the font in point (After the Profiles sectiom)*

*If you want to compile C++ programs via Powershell (like I wanted to see) then you will either need to download Visual Studio's compiler for C++, or an alternative like MinGW or MSYS2. I opted for MinGW since I am more familiar with it. Honestly, I was hoping to configure the new Windows terminal to have the same apperance and functionality as decently configured Linux or Mac terminal. So far, I have git showing with oh-my-posh, g++ installed for command-line compilation of C++ in Powershell, and Vim for in-terminal editing. Not a flawless setup (had some issues with ssh key setup in github after resetting Windows recently) but otherwise the functionality is pretty nice (minus a package manager, maybe I'll give chocolatey a try soon).*

*Unfortunately had to jump over to git bash to get my github ssh keys set up in Github*
