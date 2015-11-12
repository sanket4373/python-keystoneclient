# Ubuntu 14.04
# Ubuntu 14.04 with DevStack


# CentOS7

## Creating CentOS7 Image using CLI to your OpenStack cloud

### Step 1: logon to your server
```
ssh root@<ip address>
```

### Step 2: setting the environment variables (as a admin/root)

```
source openrc
```
### Step 3: check for list of vm images already created

```
glance image-list
```

visit this link to see the list of latest CentOS images --> 
   http://mirrors.securehost.com/centos/7/isos/x86_64/  

### Step 4:  create a directory named images inside the var directory to store all the images you download.

```
mkdir /var/images
```

### Step 5: Below command will download the required centOS7 image from the internet to the /var/images location

```
wget http://mirrors.securehost.com/centos/7/isos/x86_64/CentOS-7-x86_64 NetInstall-1503.iso -P /var/images/
```

### Step 6: Once Downloaded, use this image and create a CentOS7 image in glance

```
glance image-create --name="CentOS7" --is-public=true --disk-format=qcow2 --container-format=bare < /var/images/CentOS-7-x86_64-NetInstall-1503.iso 
```

### Step 7: Finally, check if the image is being created

```
glance image-list
```

# CentOS with Hadoop-Horton Works
# CoreOS
