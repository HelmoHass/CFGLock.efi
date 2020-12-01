# CFGLock.efi
CFGLock - unlock (MSR 0xE2) by Brumbaer

##
Some boards do not have a visible option for CFG Lock.

For those cases the Bootloaders offer options to not write to the MSR. An other way is to disable CFG Lock in the BIOS despite the fact that there is no option available in the user interface.

One way to do so is to use UEFITool, ifrextract and a patched Grub. Which is not only cumbersome, also it will work only, if the storage used for CFG Lock is in a certain varstore.

Generally speaking CFGLock.efi does what those tools do, but the only user interaction needed is to confirm that you want to toggle the CFG Lock value (on to off/off to on) and it works regardless where the CFG Lock option resides, as long as the BIOS has a CFG Lock option - hidden or not - in their HiiDatabase.

It is an EFI Application. Install it in the Tools folder of your OpenCore EFI and enter it under Misc->Tools in the config.plist.

The EFI must not be able to boot MacOS, it must just be able to show the picker.

It should also run as an application from the UEFI shell, but I haven't tested this.


###
more infos and comments
[Here](https://www.insanelymac.com/forum/topic/344035-cfglock-unlock-msr-0xe2/)

