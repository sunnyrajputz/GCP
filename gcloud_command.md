# Google Cloud CLI Commands

This document contains commonly used `gcloud` commands for managing configurations, compute instances, zones, regions, machine types, and instance groups.

---

## GCP Configuration Commands

```sh
gcloud config list project
gcloud config configurations list
gcloud config configurations activate my-default-configuration
gcloud config list
gcloud config configurations describe my-second-configuration
```

---

## Compute Engine Commands

### List Compute Instances
```sh
gcloud compute instances list
```

### Create a Compute Instance
```sh
gcloud compute instances create my-first-instance-from-gcloud
```

### Describe a Compute Instance
```sh
gcloud compute instances describe my-first-instance-from-gcloud
```

### Delete a Compute Instance
```sh
gcloud compute instances delete my-first-instance-from-gcloud
```

---

## Compute Zones and Regions

### List Zones
```sh
gcloud compute zones list
```

### List Regions
```sh
gcloud compute regions list
```

### Filter Machine Types by Zone
```sh
gcloud compute machine-types list --filter zone:asia-southeast2-b
gcloud compute machine-types list --filter "zone:(asia-southeast2-b asia-southeast2-c)"
```

### Filter Zones by Region
```sh
gcloud compute zones list --filter=region:us-west2
```

### Sort Zones by Region
```sh
gcloud compute zones list --sort-by=region
gcloud compute zones list --sort-by=~region
```

### List Zones with URI
```sh
gcloud compute zones list --uri
```

### Describe a Specific Region
```sh
gcloud compute regions describe us-west4
```

---

## Instance Templates

### List Instance Templates
```sh
gcloud compute instance-templates list
```

### Create an Instance Template
```sh
gcloud compute instance-templates create instance-template-from-command-line
```

### Delete an Instance Template
```sh
gcloud compute instance-templates delete instance-template-from-command-line
```

### Describe an Instance Template
```sh
gcloud compute instance-templates describe my-instance-template-with-custom-image
```

### Create an Instance from a Template
```sh
gcloud compute instances create my-test-vm --source-instance-template=my-instance-template-with-custom-image
```

---

## Managed Instance Groups (MIGs)

### List Managed Instance Groups
```sh
gcloud compute instance-groups managed list
```

### Create a Managed Instance Group
```sh
gcloud compute instance-groups managed create my-mig --zone us-central1-a --template my-instance-template-with-custom-image --size 1
```

### Delete a Managed Instance Group
```sh
gcloud compute instance-groups managed delete my-managed-instance-group
```

### Delete a Regional Managed Instance Group
```sh
gcloud compute instance-groups managed delete my-managed-instance-group --region=us-central1
```

### Set Autoscaling for a Managed Instance Group
```sh
gcloud compute instance-groups managed set-autoscaling my-mig --max-num-replicas=2 --zone us-central1-a
```

### Stop Autoscaling for a Managed Instance Group
```sh
gcloud compute instance-groups managed stop-autoscaling my-mig --zone us-central1-a
```

### Resize a Managed Instance Group
```sh
gcloud compute instance-groups managed resize my-mig --size=1 --zone=us-central1-a
```

### Recreate Instances in a Managed Instance Group
```sh
gcloud compute instance-groups managed recreate-instances my-mig --instances=my-mig-85fb --zone us-central1-a
```
---

📌 **Maintained by:** Sunny  
📅 **Last Updated:** 25 March 2025
