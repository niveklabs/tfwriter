# pagerduty_priority

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
module "pagerduty_priority" {
  source = "./modules/pagerduty/d/pagerduty_priority"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - The name of the priority to find in the PagerDuty API"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "pagerduty_priority" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.pagerduty_priority.this.description
}

output "id" {
  description = "returns a string"
  value       = data.pagerduty_priority.this.id
}

output "this" {
  value = pagerduty_priority.this
}
```

[top](#index)