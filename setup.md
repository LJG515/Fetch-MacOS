## Download macOS
1. Get `FetchMacOS` and place it in a known folder.

2. Open `Command Prompt` and use `cd` to go to the known folder.

3. Run `fetch-macos.exe -p PRODUCTID -o SharedSupport` where `PRODUCTID` is the macOS package you want to download.

## Edit Downloaded Files
1. Rename `InstallESDDmg.pkg` inside the `SharedSupport` folder to `InstallESD.dmg`

2. Edit `InstallInfo.plist` using WordPad (or another text editor) and remove the `chunklistURL` and `chunklistid` keys for InstallESD as well as rename `InstallESDDmg.pkg` to `InstallESD.dmg` ([example here](https://gist.github.com/foxlet/0d479afe9f2786fdfbc097025f793b88))

## Write BaseSystem to USB
1. Format the USB drive using [Boot Disk Utility](http://cvad-mac.narod.ru/files/BDU_v2.1.2018.023b.zip). Select `DL` and `Save after DL` for Clover Bootloader Source,  `Clover` for Format Options, and a `200MB Boot Partition Size` for Multi Partitioning

2. Extract `4.hfs` from `\SharedSupport\BaseSystem.dmg` --> save to it's local folder

3. Restore `4.hfs` to the USB's second partition --->  2nd partition becomes bootable "OS X Base System"

# Resize BaseStstem USB Partition
Open [Paragon Partition Manager Free](https://www.paragon-software.com/free/pm-express/) and resize the second partition of the USB drive to the full size allowed.  Don't forget to apply the changes at the end.

# Copy Additional Data
1. Open [TransMac](http://www.acutesystems.com/tmac/tmsetup.exe) and navigate to the `HFS+ Volume/Install macOS High Sierra.app/Contents` folder.  Right click anywhere in the empty space on the RHS pane and select `Copy Here`.

2.  In the next stage, select the `SharedSupport` folder we created earlier as the `Files and Folders to be copied to the Mac Volume`.