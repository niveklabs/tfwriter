# icinga2_hostgroup

[back](../icinga2.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    icinga2 = ">= 0.5.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "icinga2_hostgroup" {
  source = "./modules/icinga2/r/icinga2_hostgroup"

  # display_name - (required) is a type of string
  display_name = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "display_name" {
  description = "(required) - Display name of Host Group"
  type        = string
}

variable "name" {
  description = "(required) - name"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "icinga2_hostgroup" "this" {
  display_name = var.display_name
  name         = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = icinga2_hostgroup.this.id
}

output "this" {
  value = icinga2_hostgroup.this
}
```

[top](#index)