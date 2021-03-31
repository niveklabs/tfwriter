# exoscale_domain

[back](../exoscale.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    exoscale = ">= 0.23.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "exoscale_domain" {
  source = "./modules/exoscale/d/exoscale_domain"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - Name of the Domain"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "exoscale_domain" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.exoscale_domain.this.id
}

output "this" {
  value = exoscale_domain.this
}
```

[top](#index)