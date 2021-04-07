# google_filestore_instance

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_filestore_instance" {
  source = "./modules/google/r/google_filestore_instance"

  # description - (optional) is a type of string
  description = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # tier - (required) is a type of string
  tier = null
  # zone - (required) is a type of string
  zone = null

  file_shares = [{
    capacity_gb = null
    name        = null
  }]

  networks = [{
    ip_addresses      = []
    modes             = []
    network           = null
    reserved_ip_range = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - A description of the instance."
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional) - Resource labels to represent user-provided metadata."
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required) - The resource name of the instance."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tier" {
  description = "(required) - The service tier of the instance. Possible values: [\"TIER_UNSPECIFIED\", \"STANDARD\", \"PREMIUM\", \"BASIC_HDD\", \"BASIC_SSD\", \"HIGH_SCALE_SSD\"]"
  type        = string
}

variable "zone" {
  description = "(required) - The name of the Filestore zone of the instance."
  type        = string
}

variable "file_shares" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      capacity_gb = number
      name        = string
    }
  ))
}

variable "networks" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      ip_addresses      = list(string)
      modes             = list(string)
      network           = string
      reserved_ip_range = string
    }
  ))
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_filestore_instance" "this" {
  # description - (optional) is a type of string
  description = var.description
  # labels - (optional) is a type of map of string
  labels = var.labels
  # name - (required) is a type of string
  name = var.name
  # project - (optional) is a type of string
  project = var.project
  # tier - (required) is a type of string
  tier = var.tier
  # zone - (required) is a type of string
  zone = var.zone

  dynamic "file_shares" {
    for_each = var.file_shares
    content {
      # capacity_gb - (required) is a type of number
      capacity_gb = file_shares.value["capacity_gb"]
      # name - (required) is a type of string
      name = file_shares.value["name"]
    }
  }

  dynamic "networks" {
    for_each = var.networks
    content {
      # modes - (required) is a type of list of string
      modes = networks.value["modes"]
      # network - (required) is a type of string
      network = networks.value["network"]
      # reserved_ip_range - (optional) is a type of string
      reserved_ip_range = networks.value["reserved_ip_range"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = google_filestore_instance.this.create_time
}

output "etag" {
  description = "returns a string"
  value       = google_filestore_instance.this.etag
}

output "id" {
  description = "returns a string"
  value       = google_filestore_instance.this.id
}

output "project" {
  description = "returns a string"
  value       = google_filestore_instance.this.project
}

output "this" {
  value = google_filestore_instance.this
}
```

[top](#index)