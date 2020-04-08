# Terraform

##  官网

https://www.terraform.io/intro/index.html    



## Terraform create a gcp instance

https://www.qwiklabs.com/focuses/1208?parent=catalog

```
terraform init
terraform plan
terraform apply

terraform show


```

**instance.tf**

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

