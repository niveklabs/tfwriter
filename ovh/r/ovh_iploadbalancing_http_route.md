# ovh_iploadbalancing_http_route

[back](../ovh.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ovh = ">= 0.10.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ovh_iploadbalancing_http_route" {
  source = "./modules/ovh/r/ovh_iploadbalancing_http_route"

  # display_name - (optional) is a type of string
  display_name = null
  # frontend_id - (optional) is a type of number
  frontend_id = null
  # service_name - (required) is a type of string
  service_name = null
  # weight - (optional) is a type of number
  weight = null

  action = [{
    status = null
    target = null
    type   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "frontend_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "service_name" {
  description = "(required)"
  type        = string
}

variable "weight" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "action" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      status = number
      target = string
      type   = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "ovh_iploadbalancing_http_route" "this" {
  display_name = var.display_name
  frontend_id  = var.frontend_id
  service_name = var.service_name
  weight       = var.weight

  dynamic "action" {
    for_each = var.action
    content {
      status = action.value["status"]
      target = action.value["target"]
      type   = action.value["type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "frontend_id" {
  description = "returns a number"
  value       = ovh_iploadbalancing_http_route.this.frontend_id
}

output "id" {
  description = "returns a string"
  value       = ovh_iploadbalancing_http_route.this.id
}

output "this" {
  value = ovh_iploadbalancing_http_route.this
}
```

[top](#index)