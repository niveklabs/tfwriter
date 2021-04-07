# ad_ou

[back](../ad.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ad = ">= 0.4.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ad_ou" {
  source = "./modules/ad/d/ad_ou"

  # dn - (optional) is a type of string
  dn = null
  # name - (optional) is a type of string
  name = null
  # path - (optional) is a type of string
  path = null
}
```

[top](#index)

### Variables

```terraform
variable "dn" {
  description = "(optional) - Distinguished Name of the OU object."
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - Name of the OU object. If this is used then the `path` attribute needs to be set as well."
  type        = string
  default     = null
}

variable "path" {
  description = "(optional) - Path of the OU object. If this is used then the `Name` attribute needs to be set as well."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "ad_ou" "this" {
  # dn - (optional) is a type of string
  dn = var.dn
  # name - (optional) is a type of string
  name = var.name
  # path - (optional) is a type of string
  path = var.path
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.ad_ou.this.description
}

output "id" {
  description = "returns a string"
  value       = data.ad_ou.this.id
}

output "protected" {
  description = "returns a string"
  value       = data.ad_ou.this.protected
}

output "this" {
  value = ad_ou.this
}
```

[top](#index)