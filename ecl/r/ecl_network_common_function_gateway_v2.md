# ecl_network_common_function_gateway_v2

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
module "ecl_network_common_function_gateway_v2" {
  source = "./modules/ecl/r/ecl_network_common_function_gateway_v2"

  # common_function_pool_id - (required) is a type of string
  common_function_pool_id = null
  # description - (optional) is a type of string
  description = null
  # name - (optional) is a type of string
  name = null
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
variable "common_function_pool_id" {
  description = "(required)"
  type        = string
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
resource "ecl_network_common_function_gateway_v2" "this" {
  # common_function_pool_id - (required) is a type of string
  common_function_pool_id = var.common_function_pool_id
  # description - (optional) is a type of string
  description = var.description
  # name - (optional) is a type of string
  name = var.name
  # tenant_id - (optional) is a type of string
  tenant_id = var.tenant_id

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
output "id" {
  description = "returns a string"
  value       = ecl_network_common_function_gateway_v2.this.id
}

output "network_id" {
  description = "returns a string"
  value       = ecl_network_common_function_gateway_v2.this.network_id
}

output "subnet_id" {
  description = "returns a string"
  value       = ecl_network_common_function_gateway_v2.this.subnet_id
}

output "tenant_id" {
  description = "returns a string"
  value       = ecl_network_common_function_gateway_v2.this.tenant_id
}

output "this" {
  value = ecl_network_common_function_gateway_v2.this
}
```

[top](#index)