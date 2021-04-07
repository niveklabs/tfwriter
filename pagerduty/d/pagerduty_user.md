# pagerduty_user

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
module "pagerduty_user" {
  source = "./modules/pagerduty/d/pagerduty_user"

  # email - (required) is a type of string
  email = null
}
```

[top](#index)

### Variables

```terraform
variable "email" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "pagerduty_user" "this" {
  email = var.email
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.pagerduty_user.this.id
}

output "name" {
  description = "returns a string"
  value       = data.pagerduty_user.this.name
}

output "this" {
  value = pagerduty_user.this
}
```

[top](#index)