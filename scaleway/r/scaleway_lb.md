# scaleway_lb

[back](../scaleway.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    scaleway = ">= 2.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "scaleway_lb" {
  source = "./modules/scaleway/r/scaleway_lb"

  # ip_id - (required) is a type of string
  ip_id = null
  # name - (optional) is a type of string
  name = null
  # project_id - (optional) is a type of string
  project_id = null
  # region - (optional) is a type of string
  region = null
  # tags - (optional) is a type of list of string
  tags = []
  # type - (required) is a type of string
  type = null

  timeouts = [{
    default = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "ip_id" {
  description = "(required) - The load-balance public IP ID"
  type        = string
}

variable "name" {
  description = "(optional) - Name of the lb"
  type        = string
  default     = null
}

variable "project_id" {
  description = "(optional) - The project_id you want to attach the resource to"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - The region you want to attach the resource to"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - Array of tags to associate with the load-balancer"
  type        = list(string)
  default     = null
}

variable "type" {
  description = "(required) - The type of load-balancer you want to create"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      default = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "scaleway_lb" "this" {
  # ip_id - (required) is a type of string
  ip_id = var.ip_id
  # name - (optional) is a type of string
  name = var.name
  # project_id - (optional) is a type of string
  project_id = var.project_id
  # region - (optional) is a type of string
  region = var.region
  # tags - (optional) is a type of list of string
  tags = var.tags
  # type - (required) is a type of string
  type = var.type

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # default - (optional) is a type of string
      default = timeouts.value["default"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = scaleway_lb.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = scaleway_lb.this.ip_address
}

output "name" {
  description = "returns a string"
  value       = scaleway_lb.this.name
}

output "organization_id" {
  description = "returns a string"
  value       = scaleway_lb.this.organization_id
}

output "project_id" {
  description = "returns a string"
  value       = scaleway_lb.this.project_id
}

output "region" {
  description = "returns a string"
  value       = scaleway_lb.this.region
}

output "this" {
  value = scaleway_lb.this
}
```

[top](#index)