# linode_region

[back](../linode.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    linode = ">= 1.16.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "linode_region" {
  source = "./modules/linode/d/linode_region"

  # country - (optional) is a type of string
  country = null
}
```

[top](#index)

### Variables

```terraform
variable "country" {
  description = "(optional) - The country where this Region resides."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "linode_region" "this" {
  # country - (optional) is a type of string
  country = var.country
}
```

[top](#index)

### Outputs

```terraform
output "country" {
  description = "returns a string"
  value       = data.linode_region.this.country
}

output "id" {
  description = "returns a string"
  value       = data.linode_region.this.id
}

output "this" {
  value = linode_region.this
}
```

[top](#index)