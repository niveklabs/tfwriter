# ecl_network_network_v2

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
    ecl = ">= 2.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ecl_network_network_v2" {
  source = "./modules/ecl/r/ecl_network_network_v2"

  # admin_state_up - (optional) is a type of bool
  admin_state_up = null
  # description - (optional) is a type of string
  description = null
  # name - (optional) is a type of string
  name = null
  # plane - (optional) is a type of string
  plane = null
  # region - (optional) is a type of string
  region = null
  # tags - (optional) is a type of map of string
  tags = {}
  # tenant_id - (optional) is a type of string
  tenant_id = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "admin_state_up" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "plane" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
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
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "ecl_network_network_v2" "this" {
  admin_state_up = var.admin_state_up
  description    = var.description
  name           = var.name
  plane          = var.plane
  region         = var.region
  tags           = var.tags
  tenant_id      = var.tenant_id

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
output "admin_state_up" {
  description = "returns a bool"
  value       = ecl_network_network_v2.this.admin_state_up
}

output "id" {
  description = "returns a string"
  value       = ecl_network_network_v2.this.id
}

output "region" {
  description = "returns a string"
  value       = ecl_network_network_v2.this.region
}

output "shared" {
  description = "returns a bool"
  value       = ecl_network_network_v2.this.shared
}

output "status" {
  description = "returns a string"
  value       = ecl_network_network_v2.this.status
}

output "subnets" {
  description = "returns a list of string"
  value       = ecl_network_network_v2.this.subnets
}

output "tenant_id" {
  description = "returns a string"
  value       = ecl_network_network_v2.this.tenant_id
}

output "this" {
  value = ecl_network_network_v2.this
}
```

[top](#index)