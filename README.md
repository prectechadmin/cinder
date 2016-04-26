Cinder Driver for iXsystems===========This repo contains driver scripts for openstack block storage manipulation project called Openstack Cinder. This cinder driver will use* FreeNAS 9.3 / 9.10Requirements ===========A system running FreeNAS 9.3 / 9.10, with at minimum 8GB of memory and a minimum 20GB Disk.Another system running Devstack Kilo Release with following configurationMinimal System Requirements* RAM : 4 GB* CPU : 4 Cores* Disk : 40 GBGetting Started===========Following are steps for using iXsystems Cinder driver.```% git clone --depth=1 https://github.com/iXsystems/% cp -R ./cinder/driver/ixsystem/ /opt/stack/cinder/cinder/volume/drivers/```After following above steps, cinder driver need to be configured. Copy sample cinder.conf file and configure appropriate parameters```% cp ./cinder/driver/ixsystem/cinder.conf.sample /etc/cinder/cinder.conf```After the cinder.conf file properly configured, rejoin devstack setup to get ixsystem cinder driver attached```% cd ~/devstack/% ./rejoin-stack.sh```Using iXsystems Cinder Driver===========Following are few example commands for using iXsystems Cinder driver-To create volume -$ cinder create --name <volumeName> <volumeSizeInGB>Example$ cinder create --name TestVolume 2About Source Code=================iXsystems Cinder Driver contains following scripts -* iscsi.py - Cinder APIs are defined here. For Example - create_volume, delete_volume etc.* freenasapi.py - REST API Call routine is defined here and it contains all the methods necessary to do it.* options.py - It defines default freenas configuration parameters if those are not fetched from cinder.conf file.