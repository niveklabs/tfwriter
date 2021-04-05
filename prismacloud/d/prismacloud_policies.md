# prismacloud_policies

[back](../prismacloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    prismacloud = ">= 1.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "prismacloud_policies" {
  source = "./modules/prismacloud/d/prismacloud_policies"

  # filters - (optional) is a type of map of string
  filters = {}
}
```

[top](#index)

### Variables

```terraform
variable "filters" {
  description = "(optional) - Filter policy results"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "prismacloud_policies" "this" {
  filters = var.filters
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.prismacloud_policies.this.id
}

output "listing" {
  description = "returns a list of object"
  value       = data.prismacloud_policies.this.listing
}

output "total" {
  description = "returns a number"
  value       = data.prismacloud_policies.this.total
}

output "this" {
  value = prismacloud_policies.this
}
```

[top](#index)