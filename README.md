1. Download a Raspbian image and unzip it: 
   ```bash
   wget https://downloads.raspberrypi.org/raspbian_lite_latest --trust-server-names --continue --quiet
   unzip 2020-02-13-raspbian-buster-lite.zip
   ```
2. Download gist files:
   ```bash
   wget https://gist.githubusercontent.com/cinderblock/20952a653989e55f8a7770a0ca2348a8/raw/{prepare,chroot,grow,setup}.sh
   chmod +x {prepare,chroot,grow}.sh
   ```
3. Edit `setup.sh` as desired.
4. Run scripts:
   ```
   sudo ./prepare.sh 2020-02-13-raspbian-buster-lite.img [mount point]
   sudo ./chroot.sh 2020-02-13-raspbian-buster-lite.img [mount point]
   sudo ./grow.sh 2020-02-13-raspbian-buster-lite.img [megabytes]
   ```
   
## Prepare

Runs the `setup.sh` script in a chroot in specified image

## Chroot

Gives you a chroot in the image to change whatever manually.

*Note: Bash history will be saved too. Subject to change.*

## Grow

Grow the image (and main partition) by some number of megabytes.

This only affects the local img file. On first boot, Raspbian will automatically grow the parition to fill the full card.

*Adding 100MB adds aproximately 10 seconds to the write time when transfering to an SD card.*
