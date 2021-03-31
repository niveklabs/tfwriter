# consul_certificate_authority

[back](../consul.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    consul = ">= 2.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "consul_certificate_authority" {
  source = "./modules/consul/r/consul_certificate_authority"

  # config - (required) is a type of map of string
  config = {}
  # connect_provider - (required) is a type of string
  connect_provider = null
}
```

[top](#index)

### Variables

```terraform
variable "config" {
  description = "(required)"
  type        = map(string)
}

variable "connect_provider" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "consul_certificate_authority" "this" {
  config           = var.config
  connect_provider = var.connect_provider
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = consul_certificate_authority.this.id
}

output "this" {
  value = consul_certificate_authority.this
}
```

[top](#index)