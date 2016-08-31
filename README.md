# Kali Linux live-build-config

[Official Documentation](http://docs.kali.org/development/live-build-a-custom-kali-iso)

All variants come with **no packages predefined**, this is to make the ISO's as light as possible and the resulting install as clean as posible. If you want to add them, edit the file under live-build-config/kali-config/variant-\<variant\>/package-lists/kali.list.chroot

If you have an idea for one of my variants, I am open to suggestions. Either make the change yourself in a pull request or create an issue.

Clone a copy
```bash
apt-get install curl git live-build cdebootstrap
git clone https://github.com/St0ner1995/live-build-config.git
cd live-build-config
```

# Build ISO

To build with my custom configuration you need to specify the variant you wish to use

To build the normal ISO, run this command in the root directory of the repository

`./build.sh --distribution kali-rolling --verbose`

To build an ISO with a variant for a specific purpose (or just a diferent desktop) use the following

`./build.sh --distribution kali-rolling --variant <variant here> --verbose`

The available variants are as follows:

* Official Kali variants (from kali repository)
 * default (used by default)
 * e17
 * gnome (default is a symlink for gnome)
 * i3wm
 * kde
 * light
 * lxde
 * mate
 * xfce
* My custom variants
 * headless (No GUI, ssh enabled by default **with root login enabled**)
 * live (For USB use without install, you still need to [setup persistence](http://docs.kali.org/downloading/kali-linux-live-usb-persistence) yourself)
 

# Some Debian bugs filed for issues encountered in Kali:

[684865]: live-build: lb_binary_syslinux fails to include flavour in menu entry

[684891]: live-build: add a config parameter to define the project name

[684893]: live-build: fails to find bootloaders files when running from git checkout

[684896]: live-build: loading of build.sh does not work as expected in various scripts

