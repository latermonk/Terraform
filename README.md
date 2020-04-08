# Terraform

##  官网

https://www.terraform.io/intro/index.html    


**Terraform Learn**    
https://learn.hashicorp.com/terraform


## Get Started - Google Cloud     
https://learn.hashicorp.com/terraform?track=gcp#gcp  




## Terraform create a gcp instance    

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

