# Terraform

##  官网

https://www.terraform.io/intro/index.html    


**Terraform Learn**    
https://learn.hashicorp.com/terraform


## Get Started - Google Cloud     
https://learn.hashicorp.com/terraform?track=gcp#gcp  


##  Terraform-google-examples  
https://github.com/GoogleCloudPlatform/terraform-google-examples   


## Lab01  Terraform create a gcp instance    

https://www.qwiklabs.com/focuses/1208?parent=catalog

```
terraform init
terraform plan
terraform apply

terraform show


```

**instance.tf**

PROJECT_ID should be REPLACED by THE REAL PROJECT -  ID


```
resource "google_compute_instance" "default" {
  project      = "<PROJECT_ID>"
  name         = "terraform"
  machine_type = "n1-standard-1"
  zone         = "us-central1-a"

  boot_disk {
    initialize_params {
      image = "debian-cloud/debian-9"
    }
  }

  network_interface {
    network = "default"
    access_config {
    }
  }
}

```


##  Lab02  Create a k8s cluster 

```
terraform init
terraform apply
```

**Deploy Cloud Run on k8s Cluster**
```
gcloud container clusters update \
     tf-gke-k8s-this-is-a-new-cluster	 \
    --update-addons=CloudRun=ENABLED,HttpLoadBalancing=ENABLED \
    --zone=us-west1-b	
    
```



## Lab03  Terraform-google-nat-gateway

https://github.com/GoogleCloudPlatform/terraform-google-nat-gateway/tree/master/examples


