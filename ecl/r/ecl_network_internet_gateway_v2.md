# ecl_network_internet_gateway_v2

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
module "ecl_network_internet_gateway_v2" {
  source = "./modules/ecl/r/ecl_network_internet_gateway_v2"

  # description - (optional) is a type of string
  description = null
  # internet_service_id - (required) is a type of string
  internet_service_id = null
  # name - (optional) is a type of string
  name = null
  # qos_option_id - (required) is a type of string
  qos_option_id = null
  # region - (optional) is a type of string
  region = null
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

variable "internet_service_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "qos_option_id" {
  description = "(required)"
  type        = string
}

variable "region" {
  description = "(optional)"
  type        = string
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
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "ecl_network_internet_gateway_v2" "this" {
  description         = var.description
  internet_service_id = var.internet_service_id
  name                = var.name
  qos_option_id       = var.qos_option_id
  region              = var.region
  tenant_id           = var.tenant_id

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
output "id" {
  description = "returns a string"
  value       = ecl_network_internet_gateway_v2.this.id
}

output "region" {
  description = "returns a string"
  value       = ecl_network_internet_gateway_v2.this.region
}

output "tenant_id" {
  description = "returns a string"
  value       = ecl_network_internet_gateway_v2.this.tenant_id
}

output "this" {
  value = ecl_network_internet_gateway_v2.this
}
```

[top](#index)