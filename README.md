# Installing Fedore CoreOS using localhost ign file

## At Local Linux PC
1. Prepare ignition ign file in local Linux PC, please it in target directory, for example see fcos.ign
- Replace the IP and Gateway IP
- Replace the interface name enp0s3 
   
2. Go to target directory and start simple http server using python
  ```
  sudo python3 -m http.server 80
  ```

During installation Fedora CoroeOS machine will try to reach out to the ign file stored in local PC using http because we just created a simple-ad-hoc http server on local PC. 

## At Fedora CoreOS machine
1. Boot the Fedore CoreOS machine and install the liveCD using this command

```
sudo coreos-installer install /dev/sda \
    --insecure-ignition --ignition-url http://<local Linux PC IP>/fcos.ign
```
2. Once the installation complete, login to Fedora CoreOS machine as core user, password: core
3. Update the password

 
