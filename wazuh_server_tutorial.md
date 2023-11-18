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
