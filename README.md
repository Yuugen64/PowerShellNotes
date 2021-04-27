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
