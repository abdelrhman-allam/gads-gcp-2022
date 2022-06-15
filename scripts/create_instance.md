```bash
gcloud beta compute --project=qwiklabs-gcp-04-f0bc516a019d instances \
create dev-instance --zone=us-central1-a --machine-type=e2-medium \
--subnet=default --network-tier=PREMIUM --maintenance-policy=MIGRATE \
--service-account=551884763629-compute@developer.gserviceaccount.com \
--scopes=https://www.googleapis.com/auth/cloud-platform --tags=http-server \
--image=debian-10-buster-v20200910 --image-project=debian-cloud \
--boot-disk-size=10GB --boot-disk-type=pd-standard \
--boot-disk-device-name=dev-instance --no-shielded-secure-boot \
--no-shielded-vtpm --no-shielded-integrity-monitoring \
--reservation-affinity=any
```
```bash
gcloud compute --project=qwiklabs-gcp-04-f0bc516a019d firewall-rules \
create default-allow-http --direction=INGRESS --priority=1000 \
--network=default --action=ALLOW --rules=tcp:80 --source-ranges=0.0.0.0/0 \
--target-tags=http-server
```
```bash
gcloud compute instances create my-instance --image-family=rhel-8 \
--image-project=rhel-cloud --zone=us-central1-a
```
```bash
gcloud alpha compute instances create my-instance-1 --zone=central1-a \
--shielded-secure-boot --shielded-vtpm --shielded-integrity-monitoring
```





