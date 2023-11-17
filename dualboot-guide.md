#### [Preparing the drive](https://dortania.github.io/OpenCore-Multiboot/empty/samedisk.html)

Format your whole disk to GPT, this will ensure that macOS installer will create the necessary 200MB EFI partition that macOS requires.<br>
Once done, select "Partition", press "+" and choose the size of the other partition(s).<br>
"Format" MUST be Mac OS Extended or APFS (otherwise, macOS will convert the drive to hMBR which will break Windows installation).<br>
Hit Apply and let it do its thing !

#### [Installing Windows](https://www.youtube.com/watch?v=ztxHRGdX0Sw)

#### -- Creating Windows Partitions --

diskpart<br>
list disk<br>
select disk 0 (replace with disk number)<br>
partition efi size=100<br>
format quick fs=fat32 label="System"<br>
assign letter="S"<br>
create partition msr size=16<br>
create partition primary<br>
format quick fs=ntfs label="Windows"<br>
assign letter="W"<br>

#### -- Installing Windows (If you made installer in macOS) --

list volume<br>
exit<br>
dism /Get-WimInfo /WimFile:D:\sources\install.esd (replace D with USB drive letter)<br>
dism /Apply-Image /ImageFile:D:\sources\install.esd /Index:1 /ApplyDir:W:\ (replace D with USB drive letter)<br>
bcdboot W:\windows /s S: /f UEFI<br>

#### -- Installing Windows (If you made installer in Windows) --

list volume<br>
exit<br>
dism /Get-WimInfo /WimFile:D:\Sources\install.wim (replace D with USB drive letter)<br>
dism /Apply-Image /ImageFile:D:\Sources\install.wim /Index:1 /ApplyDir:W:\ (replace D with USB drive letter)<br>
bcdboot W:\windows /s S: /f UEFI<br>

#### [Install Windows 11 Without A Microsoft Account](https://www.youtube.com/watch?v=163V9Q6X4uM)

#### -- Commands --

Press shift+F10 to open a terminal

netsh interface show interface<br>
netsh interface set interface "interface_name" disable<br>
oobe\bypassnro<br>
