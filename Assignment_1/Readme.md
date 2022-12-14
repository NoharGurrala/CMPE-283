* Create SSH Key in the local system
```
~ ssh-keygen -t ed25519
```
* Create of VM in GCP

```
gcloud compute instances create instance-1 
--project=mythical-legend-367621 
--zone=us-central1-a 
--machine-type=n2-standard-8 
--network-interface=network-tier=PREMIUM,subnet=default 
--metadata=ssh-keys=spartan:ssh-ed25519\ AAAAC3NzaC1lZDI1NTE5AAAAINOVrGHRedev1CrZOhCl96Y6qXv1zDiajEeM8T4Ukr8K\ spartan@IMS-063MBA.local 
--maintenance-policy=MIGRATE 
--provisioning-model=STANDARD 
--service-account=620889689365-compute@developer.gserviceaccount.com 
--scopes=https://www.googleapis.com/auth/devstorage.read_only,https://www.googleapis.com/auth/logging.write,https://www.googleapis.com/auth/monitoring.write,https://www.googleapis.com/auth/servicecontrol,https://www.googleapis.com/auth/service.management.readonly,https://www.googleapis.com/auth/trace.append 
--create-disk=auto-delete=yes,boot=yes,device-name=instance-1,image=projects/ubuntu-os-cloud/global/images/ubuntu-1804-bionic-v20221018,mode=rw,size=10,type=projects/mythical-legend-367621/zones/us-central1-a/diskTypes/pd-ssd 
--no-shielded-secure-boot 
--shielded-vtpm 
--shielded-integrity-monitoring 
--reservation-affinity=any 
--min-cpu-platform "Intel Cascade Lake" 
--enable-nested-virtualization
```

* Make Directory to upload the files and execute

```
~ mkdir virtualization1
~ cd virtualization1
```

* Upload the file into the VM using SSH
./
```
~ mv cmpe2831.c virtualization1
~ mv Makefile virtualization1/
```

* Installing the packages requiured

```
~ sudo apt-get update
~ sudo apt-get upgrade
```

* Make code ready to run the code 
```
~ sudo apt-get install vim gcc make linux-headers-$(uname -r)

~ sudo make
```

* Running the Code 
```
~ sudo insmod ./cmpe2831.ko
```

* Displaying the command
```
~ sudo dmesg
```

By Running the commands with code from the files you will get result displayed and the files are generated in the folder.
