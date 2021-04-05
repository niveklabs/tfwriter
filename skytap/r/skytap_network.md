# skytap_network

[back](../skytap.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    skytap = ">= 0.14.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "skytap_network" {
  source = "./modules/skytap/r/skytap_network"

  # domain - (required) is a type of string
  domain = null
  # environment_id - (required) is a type of string
  environment_id = null
  # gateway - (optional) is a type of string
  gateway = null
  # name - (required) is a type of string
  name = null
  # subnet - (required) is a type of string
  subnet = null
  # tunnelable - (optional) is a type of bool
  tunnelable = null

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
variable "domain" {
  description = "(required)"
  type        = string
}

variable "environment_id" {
  description = "(required)"
  type        = string
}

variable "gateway" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "subnet" {
  description = "(required)"
  type        = string
}

variable "tunnelable" {
  description = "(optional)"
  type        = bool
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
resource "skytap_network" "this" {
  domain         = var.domain
  environment_id = var.environment_id
  gateway        = var.gateway
  name           = var.name
  subnet         = var.subnet
  tunnelable     = var.tunnelable

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
output "gateway" {
  description = "returns a string"
  value       = skytap_network.this.gateway
}

output "id" {
  description = "returns a string"
  value       = skytap_network.this.id
}

output "this" {
  value = skytap_network.this
}
```

[top](#index)