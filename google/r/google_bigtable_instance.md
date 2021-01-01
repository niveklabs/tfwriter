# google_bigtable_instance

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    google = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "google_bigtable_instance" {
  source = "./modules/google/r/google_bigtable_instance"

  # deletion_protection - (optional) is a type of bool
  deletion_protection = null
  # display_name - (optional) is a type of string
  display_name = null
  # instance_type - (optional) is a type of string
  instance_type = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null

  cluster = [{
    cluster_id   = null
    num_nodes    = null
    storage_type = null
    zone         = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "deletion_protection" {
  description = "(optional) - Whether or not to allow Terraform to destroy the instance. Unless this field is set to false in Terraform state, a terraform destroy or terraform apply that would delete the instance will fail."
  type        = bool
  default     = null
}

variable "display_name" {
  description = "(optional) - The human-readable display name of the Bigtable instance. Defaults to the instance name."
  type        = string
  default     = null
}

variable "instance_type" {
  description = "(optional) - The instance type to create. One of \"DEVELOPMENT\" or \"PRODUCTION\". Defaults to \"PRODUCTION\"."
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional) - A mapping of labels to assign to the resource."
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required) - The name (also called Instance Id in the Cloud Console) of the Cloud Bigtable instance."
  type        = string
}

variable "project" {
  description = "(optional) - The ID of the project in which the resource belongs. If it is not provided, the provider project is used."
  type        = string
  default     = null
}

variable "cluster" {
  description = "nested mode: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      cluster_id   = string
      num_nodes    = number
      storage_type = string
      zone         = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```hcl
resource "google_bigtable_instance" "this" {
  deletion_protection = var.deletion_protection
  display_name        = var.display_name
  instance_type       = var.instance_type
  labels              = var.labels
  name                = var.name
  project             = var.project

  dynamic "cluster" {
    for_each = var.cluster
    content {
      cluster_id   = cluster.value["cluster_id"]
      num_nodes    = cluster.value["num_nodes"]
      storage_type = cluster.value["storage_type"]
      zone         = cluster.value["zone"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "display_name" {
  description = "returns a string"
  value       = google_bigtable_instance.this.display_name
}

output "id" {
  description = "returns a string"
  value       = google_bigtable_instance.this.id
}

output "project" {
  description = "returns a string"
  value       = google_bigtable_instance.this.project
}

output "this" {
  value = google_bigtable_instance.this
}
```

[top](#index)