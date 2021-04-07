# pagerduty_user_contact_method

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
module "pagerduty_user_contact_method" {
  source = "./modules/pagerduty/d/pagerduty_user_contact_method"

  # label - (required) is a type of string
  label = null
  # type - (required) is a type of string
  type = null
  # user_id - (required) is a type of string
  user_id = null
}
```

[top](#index)

### Variables

```terraform
variable "label" {
  description = "(required) - The name of the contact method to find in the PagerDuty API"
  type        = string
}

variable "type" {
  description = "(required) - The type of the contact method"
  type        = string
}

variable "user_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "pagerduty_user_contact_method" "this" {
  label   = var.label
  type    = var.type
  user_id = var.user_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.pagerduty_user_contact_method.this.id
}

output "this" {
  value = pagerduty_user_contact_method.this
}
```

[top](#index)