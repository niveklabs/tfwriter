# vra_flavor_profile

[back](../vra.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vra = ">= 0.3.5"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vra_flavor_profile" {
  source = "./modules/vra/r/vra_flavor_profile"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # region_id - (required) is a type of string
  region_id = null

  flavor_mapping = [{
    cpu_count     = null
    instance_type = null
    memory        = null
    name          = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "region_id" {
  description = "(required)"
  type        = string
}

variable "flavor_mapping" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      cpu_count     = number
      instance_type = string
      memory        = number
      name          = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "vra_flavor_profile" "this" {
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # region_id - (required) is a type of string
  region_id = var.region_id

  dynamic "flavor_mapping" {
    for_each = var.flavor_mapping
    content {
      # cpu_count - (optional) is a type of number
      cpu_count = flavor_mapping.value["cpu_count"]
      # instance_type - (optional) is a type of string
      instance_type = flavor_mapping.value["instance_type"]
      # memory - (optional) is a type of number
      memory = flavor_mapping.value["memory"]
      # name - (required) is a type of string
      name = flavor_mapping.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "cloud_account_id" {
  description = "returns a string"
  value       = vra_flavor_profile.this.cloud_account_id
}

output "created_at" {
  description = "returns a string"
  value       = vra_flavor_profile.this.created_at
}

output "external_region_id" {
  description = "returns a map of string"
  value       = vra_flavor_profile.this.external_region_id
}

output "id" {
  description = "returns a string"
  value       = vra_flavor_profile.this.id
}

output "links" {
  description = "returns a set of object"
  value       = vra_flavor_profile.this.links
}

output "org_id" {
  description = "returns a string"
  value       = vra_flavor_profile.this.org_id
}

output "owner" {
  description = "returns a string"
  value       = vra_flavor_profile.this.owner
}

output "updated_at" {
  description = "returns a string"
  value       = vra_flavor_profile.this.updated_at
}

output "this" {
  value = vra_flavor_profile.this
}
```

[top](#index)