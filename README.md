# Refind OLED No Blind Me


### Installation

Copy the theme folder to a `themes` directory inside the refind EFI directory (usually `/boot/EFI/refind`)
>

	**Example**                                               (right click to open terminal in downloads folder)
	sudo mkdir /boot/EFI/refind/themes                        (ignore command or error if directory exists)
	sudo cp -r ./RONBM /boot/EFI/refind/themes/RONBM

Then add `include themes/RONBM/theme.conf` at the end of /boot/EFI/refind/refind.conf
>

	sudo nano /boot/EFI/refind/refind.conf                    (ctrl+u to paste, ctrl+s to save, ctrl+x to exit)


### Customization

Open /RONBM/theme.conf and follow directions to edit:

* Timeout before automatic boot
* Maximum number of icons shown
* Icon size

May want to resize background.png to monitor resolution. There is an activity dot in the top right corner (doesn't really serve any practical purpose) that can be kept or cropped out.

To apply a specific icon for some distros it may be necessary to add a boot stanza to /boot/EFI/refind/refind.conf

### Example
>

	menuentry " ****** " {                                      (replace ****** with OS name)
		icon /EFI/refind/themes/RONBM/icons/******.png          (replace ****** with icon name)
	    loader /vmlinuz-linux-******                            (replace ****** to match file name in /boot )
	    initrd /initramfs-linux-******.img                      (replace ****** to match file name in /boot )
	    options "quiet ******"                                  (replace "quiet ******" with boot options)
	    }
    
Boot options may be found in refind_linux.conf (sudo nano /boot/refind_linux.conf).   Copy the long string in quotes after "Boot with standard options"

