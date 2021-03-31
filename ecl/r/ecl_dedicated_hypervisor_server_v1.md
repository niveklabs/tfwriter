# ecl_dedicated_hypervisor_server_v1

[back](../ecl.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ecl = ">= 1.13.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ecl_dedicated_hypervisor_server_v1" {
  source = "./modules/ecl/r/ecl_dedicated_hypervisor_server_v1"

  # admin_pass - (optional) is a type of string
  admin_pass = null
  # availability_zone - (optional) is a type of string
  availability_zone = null
  # description - (optional) is a type of string
  description = null
  # flavor_ref - (required) is a type of string
  flavor_ref = null
  # image_ref - (required) is a type of string
  image_ref = null
  # metadata - (optional) is a type of map of string
  metadata = {}
  # name - (required) is a type of string
  name = null

  networks = [{
    fixed_ip        = null
    plane           = null
    port            = null
    segmentation_id = null
    uuid            = null
  }]

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "admin_pass" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "availability_zone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "flavor_ref" {
  description = "(required)"
  type        = string
}

variable "image_ref" {
  description = "(required)"
  type        = string
}

variable "metadata" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "networks" {
  description = "nested block: NestingList, min items: 1, max items: 4"
  type = set(object(
    {
      fixed_ip        = string
      plane           = string
      port            = string
      segmentation_id = number
      uuid            = string
    }
  ))
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "ecl_dedicated_hypervisor_server_v1" "this" {
  admin_pass        = var.admin_pass
  availability_zone = var.availability_zone
  description       = var.description
  flavor_ref        = var.flavor_ref
  image_ref         = var.image_ref
  metadata          = var.metadata
  name              = var.name

  dynamic "networks" {
    for_each = var.networks
    content {
      fixed_ip        = networks.value["fixed_ip"]
      plane           = networks.value["plane"]
      port            = networks.value["port"]
      segmentation_id = networks.value["segmentation_id"]
      uuid            = networks.value["uuid"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "admin_pass" {
  description = "returns a string"
  value       = ecl_dedicated_hypervisor_server_v1.this.admin_pass
}

output "availability_zone" {
  description = "returns a string"
  value       = ecl_dedicated_hypervisor_server_v1.this.availability_zone
}

output "baremetal_server_id" {
  description = "returns a string"
  value       = ecl_dedicated_hypervisor_server_v1.this.baremetal_server_id
}

output "id" {
  description = "returns a string"
  value       = ecl_dedicated_hypervisor_server_v1.this.id
}

output "this" {
  value = ecl_dedicated_hypervisor_server_v1.this
}
```

[top](#index)