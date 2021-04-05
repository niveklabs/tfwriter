# ecl_network_load_balancer_plan_v2

[back](../ecl.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "ecl_network_load_balancer_plan_v2" {
  source = "./modules/ecl/d/ecl_network_load_balancer_plan_v2"

  # description - (optional) is a type of string
  description = null
  # enabled - (optional) is a type of bool
  enabled = null
  # maximum_syslog_servers - (optional) is a type of number
  maximum_syslog_servers = null
  # name - (optional) is a type of string
  name = null
  # vendor - (optional) is a type of string
  vendor = null
  # version - (optional) is a type of string
  version = null

  model = [{
    edition = null
    size    = null
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

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "maximum_syslog_servers" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vendor" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "model" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      edition = string
      size    = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "ecl_network_load_balancer_plan_v2" "this" {
  description            = var.description
  enabled                = var.enabled
  maximum_syslog_servers = var.maximum_syslog_servers
  name                   = var.name
  vendor                 = var.vendor
  version                = var.version

  dynamic "model" {
    for_each = var.model
    content {
      edition = model.value["edition"]
      size    = model.value["size"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.ecl_network_load_balancer_plan_v2.this.description
}

output "enabled" {
  description = "returns a bool"
  value       = data.ecl_network_load_balancer_plan_v2.this.enabled
}

output "id" {
  description = "returns a string"
  value       = data.ecl_network_load_balancer_plan_v2.this.id
}

output "maximum_syslog_servers" {
  description = "returns a number"
  value       = data.ecl_network_load_balancer_plan_v2.this.maximum_syslog_servers
}

output "name" {
  description = "returns a string"
  value       = data.ecl_network_load_balancer_plan_v2.this.name
}

output "vendor" {
  description = "returns a string"
  value       = data.ecl_network_load_balancer_plan_v2.this.vendor
}

output "version" {
  description = "returns a string"
  value       = data.ecl_network_load_balancer_plan_v2.this.version
}

output "this" {
  value = ecl_network_load_balancer_plan_v2.this
}
```

[top](#index)