## Now Deploy Wazuh SIEM

Create a new ubuntu instance on google cloud with this code this code on google cloud cli.

```bash
gcloud compute instances create wazuhserver --project=even-timing-396709 --zone=us-central1-a --machine-type=e2-medium --network-interface=network-tier=PREMIUM,stack-type=IPV4_ONLY,subnet=default --maintenance-policy=MIGRATE --provisioning-model=STANDARD --service-account=22420940236-compute@developer.gserviceaccount.com --scopes=https://www.googleapis.com/auth/devstorage.read_only,https://www.googleapis.com/auth/logging.write,https://www.googleapis.com/auth/monitoring.write,https://www.googleapis.com/auth/servicecontrol,https://www.googleapis.com/auth/service.management.readonly,https://www.googleapis.com/auth/trace.append --create-disk=auto-delete=yes,boot=yes,device-name=wazuh-server,image=projects/ubuntu-os-cloud/global/images/ubuntu-2004-focal-v20231101,mode=rw,size=20,type=projects/even-timing-396709/zones/us-central1-a/diskTypes/pd-balanced --no-shielded-secure-boot --shielded-vtpm --shielded-integrity-monitoring --labels=goog-ec-src=vm_add-gcloud --reservation-affinity=any
````

connect to the ubuntu server and run this code.

```bash
curl -sO https://packages.wazuh.com/4.6/wazuh-install.sh && sudo bash ./wazuh-install.sh -a
```

once done installing it will give an output with username and password ( Note : Save It )
```bash
sudo tar -O -xvf wazuh-install-files.tar wazuh-install-files/wazuh-passwords.txt
```
![](https://i.imgur.com/s8uNtcU.png)

## Now Go to the twingate tutorial as it will make your life easier as you will not have access private ip on which wazuh is

Now Log into the SIEM 

![](https://i.imgur.com/Pg3HdUa.png)

![](https://i.imgur.com/O1IrdNq.png)

## Now lets deploy an agent

![](https://i.imgur.com/9rkbuN6.png)

Important ( Enter the wazuh server ip address into the server address that the agent will send back data to )

![](https://i.imgur.com/ernigVG.png)

Copy the command and paste it into the instance you wish to install the agent on.

## Now lets check Security configuration assessment 
A security assessment configuration typically refers to the process of evaluating and configuring various aspects of an organization's information technology infrastructure to enhance security. This process involves reviewing and adjusting settings, policies, and configurations to align with security best practices and mitigate potential risks. 
It will also tell as to how to fix those problems and for that plz look at the "Security Assessment Configuration" tutorial in the repo. 
![](https://i.imgur.com/FHstswk.png)

## Now lets check Vulnerability section. ( It scans the the agent os and tell of all vulnerbilities on the system )

First we will have to enable it as it is off default

![](https://i.imgur.com/utd70tl.png)

click on edit configuration and change setting and save it

![](https://i.imgur.com/SlzqaeB.png)

Now go to vulnerabilities and check it ( If none appears dont panic as there will be none according to the scan )
![](https://i.imgur.com/iXWklVh.png)


## Now lets check Security Events where all of windows log will appear

![](https://i.imgur.com/J598k1g.png)

![](https://i.imgur.com/MbiHtFr.png)


## Now to monitor a specific directory in the instance on which agent is installed

Open the instance and go to the C:\Program Files (x86)\ossec-agent and open win32ui

Now open the config file from view to view config file and add some directory like and add it below 32 bit program else it wont work 

<directories realtime="yes" report_changes="yes" check_all="yes">C:\Users\Administrator\Desktop</directories>

![](https://i.imgur.com/3DYEq4C.png)

Now save it and restart the agent

Now monitor the screen any changes made into the directory through integrity monitoring system

https://i.imgur.com/fO0Q6kT.png

![](https://i.imgur.com/fO0Q6kT.png)


///The End
