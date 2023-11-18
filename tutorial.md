# My Awesome Project

Welcome to my awesome project! This project aims to automate the setup and configuration of Active Directory on Google Cloud Platform, integrating it with other instances, deploying the Wazuh SIEM for monitoring, and implementing secure remote connections through Twingate. The end goal is to create a robust and secure environment for managing and monitoring instances in a cloud-based infrastructure., and here's how you can set it up:

## Prerequisites
- Google Cloud Subscription ( Free Awailable on Google Cloud ) 


## Usage

To create a Google Cloud VM instance, use the following command on google cloud cli:

```bash
gcloud compute instances create active-directory --project=even-timing-396709 --zone=us-central1-a --machine-type=e2-medium --network-interface=network-tier=PREMIUM,stack-type=IPV4_ONLY,subnet=default --maintenance-policy=MIGRATE --provisioning-model=STANDARD --service-account=22420940236-compute@developer.gserviceaccount.com --scopes=https://www.googleapis.com/auth/devstorage.read_only,https://www.googleapis.com/auth/logging.write,https://www.googleapis.com/auth/monitoring.write,https://www.googleapis.com/auth/servicecontrol,https://www.googleapis.com/auth/service.management.readonly,https://www.googleapis.com/auth/trace.append --create-disk=auto-delete=yes,boot=yes,device-name=instance-1,image=projects/windows-cloud/global/images/windows-server-2022-dc-v20231115,mode=rw,size=50,type=projects/even-timing-396709/zones/us-central1-a/diskTypes/pd-balanced --no-shielded-secure-boot --shielded-vtpm --shielded-integrity-monitoring --labels=goog-ec-src=vm_add-gcloud --reservation-affinity=any
```
Log into the instance using RDP and server manager will open up with this screen.

![](https://i.imgur.com/r7thVEp.png)

Click Add Role and feature.

![](https://i.imgur.com/M2h2esh.png)

Now Install it.

![](https://i.imgur.com/dtJJ77O.png)

Click promote this server to domain controller.

![](https://i.imgur.com/2ZUWE5K.png)

Add domain name.

![](https://i.imgur.com/n6OJVqg.png)

Add password and click next.

![](https://i.imgur.com/4kS5mhf.png)

Install.

![](https://i.imgur.com/M2h2esh.png)

If this error pops up it means that the local admin account password criteria is not met since it will become domain admin.

![](https://i.imgur.com/4Kcin0i.png)


Lets change local admin account password and enter a password that match the minimum criteria.

![](https://i.imgur.com/LVdrjbt.png)


Now click prerequisite recheck and everything will be done.


## Creating User

Create a user.

![](https://i.imgur.com/8qwQ9fO.png)

Now lets assign him to be admin using predefined objects. This will allow this user to log in from anywhere into the domain controller.

![](https://i.imgur.com/aqXy84p.png)

