# exoscale_domain

[back](../exoscale.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    exoscale = ">= 0.23.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "exoscale_domain" {
  source = "./modules/exoscale/r/exoscale_domain"

  # name - (required) is a type of string
  name = null

  timeouts = [{
    create = null
    delete = null
    read   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      read   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "exoscale_domain" "this" {
  name = var.name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      read   = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "auto_renew" {
  description = "returns a bool"
  value       = exoscale_domain.this.auto_renew
}

output "expires_on" {
  description = "returns a string"
  value       = exoscale_domain.this.expires_on
}

output "id" {
  description = "returns a string"
  value       = exoscale_domain.this.id
}

output "state" {
  description = "returns a string"
  value       = exoscale_domain.this.state
}

output "token" {
  description = "returns a string"
  value       = exoscale_domain.this.token
}

output "this" {
  value = exoscale_domain.this
}
```

[top](#index)