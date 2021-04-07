# ovh_iploadbalancing_refresh

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
    ovh = ">= 0.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ovh_iploadbalancing_refresh" {
  source = "./modules/ovh/r/ovh_iploadbalancing_refresh"

  # keepers - (required) is a type of list of string
  keepers = []
  # service_name - (required) is a type of string
  service_name = null
}
```

[top](#index)

### Variables

```terraform
variable "keepers" {
  description = "(required)"
  type        = list(string)
}

variable "service_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "ovh_iploadbalancing_refresh" "this" {
  # keepers - (required) is a type of list of string
  keepers = var.keepers
  # service_name - (required) is a type of string
  service_name = var.service_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = ovh_iploadbalancing_refresh.this.id
}

output "this" {
  value = ovh_iploadbalancing_refresh.this
}
```

[top](#index)