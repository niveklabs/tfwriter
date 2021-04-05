# sdm_resource

[back](../sdm.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    sdm = ">= 1.0.19"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "sdm_resource" {
  source = "./modules/sdm/d/sdm_resource"

  # hostname - (optional) is a type of string
  hostname = null
  # name - (optional) is a type of string
  name = null
  # port - (optional) is a type of number
  port = null
  # type - (optional) is a type of string
  type = null
  # username - (optional) is a type of string
  username = null

  timeouts = [{
    default = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "hostname" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "username" {
  description = "(optional)"
  type        = string
  default     = null
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

### Datasource

```terraform
data "sdm_resource" "this" {
  hostname = var.hostname
  name     = var.name
  port     = var.port
  type     = var.type
  username = var.username

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
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
  value       = data.sdm_resource.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.sdm_resource.this.ids
}

output "resources" {
  description = "returns a list of object"
  value       = data.sdm_resource.this.resources
}

output "this" {
  value = sdm_resource.this
}
```

[top](#index)