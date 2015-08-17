# todo
## Rebuild Lenovo
1. Assess size of existing Windows build and program files.
1. Use [this application](http://www.nirsoft.net/utils/produkey-x64.zip) to retrieve the Windows product key from the registry, as per the instructions on [this page](http://www.howtogeek.com/206329/how-to-find-your-lost-windows-or-office-product-keys/)
1. FAILED: Attempt to download Windows install media using that key [here](http://www.microsoft.com/en-us/software-recovery). Get "`Refer to Message Code 715-123130`" error.
1. Use [this tool](http://wudt.codeplex.com/) to turn an ISO ripped from my own purchased Windows 7 Pro OEM install DVD to a bootable USB drive.
1. (If the above fails, consider [resizing the existing partition](http://www.bleepingcomputer.com/tutorials/shrink-and-extend-ntfs-volumes-in-windows/) and creating a new D: as per below. You might also want to create recovery media from the existing D:, although you can order media in the post. [Ugh!]).
1. Install Windows, wiping all partitions and allocating 80GB to C: `System` and the rest to D: `Data`. Both NTFS.
1. Make sure TRIM is enabled for the SSD, run `fsutil behavior query DisableDeleteNotify`. See [here](http://lifehacker.com/5640971/check-if-trim-is-enabled-for-your-solid-state-drive-in-windows-7) for more details.
1. Run Windows Update.
1. Install Lenovo-specific thingumies, in no particular order:
  * [Synaptics Driver](https://download.lenovo.com/ibmdl/pub/pc/pccbbs/mobiles/n10gw22w.exe)
  * [Intel LAN Driver](https://download.lenovo.com/ibmdl/pub/pc/pccbbs/mobiles/nz0rw03w_64.exe) if it didn't get detected already. [Intel WLAN Driver](https://download.lenovo.com/ibmdl/pub/pc/pccbbs/mobiles/n1gw202w_64.exe) again, only if needed.
  * [Intel Chipset Support](https://download.lenovo.com/pccbbs/mobiles/n10ic14w.exe)
  * [Intel HD Graphics Support](https://download.lenovo.com/ibmdl/pub/pc/pccbbs/mobiles/nz0d602w.exe) NB: See if Windows Update grabs this first!
  * [Intel USB 3.0 Driver](https://download.lenovo.com/ibmdl/pub/pc/pccbbs/mobiles/n10ys08w.exe) and also [ThinkPad Dock Driver](https://download.lenovo.com/ibmdl/pub/pc/pccbbs/mobiles/hlup01ww.exe).
  * [INF for ThinkPad monitor panel](https://download.lenovo.com/ibmdl/pub/pc/pccbbs/mobiles/groi11ww.exe)
  * [Hotkey Features Integration](https://download.lenovo.com/ibmdl/pub/pc/pccbbs/mobiles/n1avu31w.exe)
  * [ThinkPad Smart Mark](https://download.lenovo.com/ibmdl/pub/pc/pccbbs/mobiles/tpsm_v112.exe) NB: Try without this first!
  * [Lenovo Fingerprint Manager](https://download.lenovo.com/ibmdl/pub/pc/pccbbs/mobiles/lz4goaa2_64.exe) NB: Does Windows support this natively? Check first.
  * [Lenovo Power Management Driver](https://download.lenovo.com/ibmdl/pub/pc/pccbbs/mobiles/n1cku18w.exe) does Winodws support switching batteries natively? Probably, in which case don't bother with this.
  * [Intel Storage Driver](https://download.lenovo.com/pccbbs/mobiles/nz0io01w.exe). Does the storage appear to be working, and are there any devices shown as unrecognised in Device Manager? If all OK, skip this.
1. [Download](http://download.eset.com/special/live-installer/eset_nod32_antivirus_live_installer.exe) and install NOD32 antivirus, see my email for the licence key.
1. Set up SMB shares to Moneyshot (pegged at `192.168.1.10`) for,
  1. Data D: (stripe)
  1. DVD drive (for the below)
1. Install Adobe CS 5.5 from DVD in loft. See `D:\Apps...` for the key I purchased on Moneyshot.
1. Test editing with some AVCHD copied across manually.
1. TODO: Robocopy
1. TODO: Encrypt hard drive https://en.wikipedia.org/wiki/VeraCrypt
  * TPM?
  * Does the machine support it already? https://support.lenovo.com/en/documents/ht002240?tabName=Solutions
  * ??? Profit!
