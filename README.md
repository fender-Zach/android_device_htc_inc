CM10.1 for the Droid Incredible

## Info
[**XDA Discussion thread**](http://forum.xda-developers.com/showthread.php?p=37860499#post37860499)

### Initialize
[Setup Linux/OS X](http://source.android.com/source/initializing.html) - Please note: it must be sun-java-6, not openjdk

### Prepare to download sources
```bash
mkdir ~/PAC4.2
mkdir ~/bin
cd ~/cm10/
curl https://dl-ssl.google.com/dl/googlesource/git-repo/repo > ~/bin/repo
chmod a+x ~/bin/repo
repo init -u git://github.com/PAC-man/android.git -b cm-10.1
```

### Finish setting up repo
```bash
wget -O .repo/local_manifest.xml https://raw.github.com/fender-Zach/android_device_htc_inc/patch-1/Manifest/local_manifest.xml
```

### Download the source
```bash
cd ~/PAC4.2
repo sync 
```
NOTE: This WILL take a long time.

Build Fixes

cd ~/PACMANROM/android  git revert ce48f5d  and git revert 7434a2b
cd ~/PACMANROM/hardware/libhardware  git revert 5b70e9b2

### Build
Make sure we're in ~/cm10...
```bash
cd ~/PAC4.2
```
Make The Vendors)...
Android Products Put it into vendor/pac/products http://d-h.st/C8i
pac_inc.mk Put into vendor/pac/products http://d-h.st/3S0

And build!
```bash
./build-pac.sh inc
```

