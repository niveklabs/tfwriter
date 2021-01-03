# checkpoint_management_nat_section

[back](../checkpoint.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    checkpoint = ">= 1.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "checkpoint_management_nat_section" {
  source = "./modules/checkpoint/d/checkpoint_management_nat_section"

  # name - (optional) is a type of string
  name = null
  # package - (required) is a type of string
  package = null
  # uid - (optional) is a type of string
  uid = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional) - Object name."
  type        = string
  default     = null
}

variable "package" {
  description = "(required) - Name of the package."
  type        = string
}

variable "uid" {
  description = "(optional) - Object unique identifier."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "checkpoint_management_nat_section" "this" {
  name    = var.name
  package = var.package
  uid     = var.uid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.checkpoint_management_nat_section.this.id
}

output "this" {
  value = checkpoint_management_nat_section.this
}
```

[top](#index)