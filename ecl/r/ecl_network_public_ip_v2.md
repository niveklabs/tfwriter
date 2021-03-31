# ecl_network_public_ip_v2

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
module "ecl_network_public_ip_v2" {
  source = "./modules/ecl/r/ecl_network_public_ip_v2"

  # description - (optional) is a type of string
  description = null
  # internet_gw_id - (required) is a type of string
  internet_gw_id = null
  # name - (optional) is a type of string
  name = null
  # region - (optional) is a type of string
  region = null
  # submask_length - (required) is a type of number
  submask_length = null
  # tenant_id - (optional) is a type of string
  tenant_id = null

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
  description = "(optional)"
  type        = string
  default     = null
}

variable "internet_gw_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "submask_length" {
  description = "(required)"
  type        = number
}

variable "tenant_id" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "ecl_network_public_ip_v2" "this" {
  description    = var.description
  internet_gw_id = var.internet_gw_id
  name           = var.name
  region         = var.region
  submask_length = var.submask_length
  tenant_id      = var.tenant_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "cidr" {
  description = "returns a string"
  value       = ecl_network_public_ip_v2.this.cidr
}

output "id" {
  description = "returns a string"
  value       = ecl_network_public_ip_v2.this.id
}

output "region" {
  description = "returns a string"
  value       = ecl_network_public_ip_v2.this.region
}

output "tenant_id" {
  description = "returns a string"
  value       = ecl_network_public_ip_v2.this.tenant_id
}

output "this" {
  value = ecl_network_public_ip_v2.this
}
```

[top](#index)