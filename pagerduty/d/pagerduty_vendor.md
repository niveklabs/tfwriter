# pagerduty_vendor

[back](../pagerduty.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    pagerduty = ">= 1.9.6"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "pagerduty_vendor" {
  source = "./modules/pagerduty/d/pagerduty_vendor"

  # name - (required) is a type of string
  name = null
  # name_regex - (optional) is a type of string
  name_regex = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "name_regex" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "pagerduty_vendor" "this" {
  name       = var.name
  name_regex = var.name_regex
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.pagerduty_vendor.this.id
}

output "type" {
  description = "returns a string"
  value       = data.pagerduty_vendor.this.type
}

output "this" {
  value = pagerduty_vendor.this
}
```

[top](#index)