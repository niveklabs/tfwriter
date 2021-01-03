# pagerduty_business_service

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
    pagerduty = ">= 1.8.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "pagerduty_business_service" {
  source = "./modules/pagerduty/d/pagerduty_business_service"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "pagerduty_business_service" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.pagerduty_business_service.this.id
}

output "this" {
  value = pagerduty_business_service.this
}
```

[top](#index)