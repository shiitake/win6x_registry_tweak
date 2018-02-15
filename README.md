# win6x_registry_tweak
*This little tool un-hides "packages" like Windows Media Center/Player, IE, IIS, Games, etc... so you can lower the size of your install.wim*

### Important Disclaimer: I did not write this code.  

#### I've added it to github for posterity sake. It has been floating around for years and was recently mentioned on reddit. It looks like several people have worked on it. The most recent (that I found) was Legolash2o on the [msfn.org forums](https://msfn.org/board/topic/152688-win6x_registry_tweak/). Possibly this github user by the same name https://github.com/Legolash2o.

I cannot offer any support or bug fixes; I have not built the project and will most likely not merge any pull requests. Feel free to fork the repo. 

##### The latest notes from the forum post above include the following: 

Top left is un-hiding a specific package, top right is writing the log of available files to a txt file, bottom left is un-hiding all components of an image and finally the bottom right is un-hiding all the packages from current installed OS.

*install_wim_tweak.exe /?*  
This will show all available options..  

*install_wim_tweak.exe /p <MountPath>*  
This will unhide all the packages in the selected image

*install_wim_tweak.exe /o*  
This will unhide all the packages on the currently installed OS

*install_wim_tweak.exe /p <MountPath> /l*  
This will list all the packages available in the selected image and write them to a text file in the same directory.

*install_wim_tweak.exe /o /l*  
This will list all the packages available on the installed OS and write them to a text file in the same directory.

*install_wim_tweaks.exe /p <MountPath> /c Microsoft-Windows-.........*  
This will just inhide the selected component from the selected image, can also be used with /o. If you add /r at the end it will remove the package.

**Changes made from the original version by wnuku**

- /h will restore them to default (must use without /h first)
- /n will not create backups (faster)
- /d will not delete owners keys.
- /m is no longer needed, will do the task by default
- /l will output a list of all packages to a text file.
- /o will use currently installed image.
- fixed a bug where it did not work if there was a space in the mountpath.
- /c <PackageName> will un-hide specific package
- using /r with /c will remove the package
- Win32Security.dll file is no longer needed
- Added new colours, errors are displayed in Red
- Fixed bug crashing at end of running
- Fixed bug where it cannot unmount registry if something fails
- Added specific component selection
- Fixed some other bugs
- Added an appropriate small icon for the app

*Also normally you will have to put the specific component name i.e.
"/c Microsoft-Hyper-V-Common-Drivers-Package~31bf3856ad364e35~x86~~6.1.7601.17514"
but if for example you put "/c Microsoft-Hyper-V-Common-Drivers-Package" it will show all packages starting with that.*
