# ovh_me_installation_template_partition_scheme

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
module "ovh_me_installation_template_partition_scheme" {
  source = "./modules/ovh/r/ovh_me_installation_template_partition_scheme"

  # name - (required) is a type of string
  name = null
  # priority - (required) is a type of number
  priority = null
  # template_name - (required) is a type of string
  template_name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - name of this partitioning scheme"
  type        = string
}

variable "priority" {
  description = "(required) - on a reinstall, if a partitioning scheme is not specified, the one with the higher priority will be used by default, among all the compatible partitioning schemes (given the underlying hardware specifications)"
  type        = number
}

variable "template_name" {
  description = "(required) - This template name"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "ovh_me_installation_template_partition_scheme" "this" {
  name          = var.name
  priority      = var.priority
  template_name = var.template_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = ovh_me_installation_template_partition_scheme.this.id
}

output "this" {
  value = ovh_me_installation_template_partition_scheme.this
}
```

[top](#index)