# ad_ou

[back](../ad.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
  source = "./modules/ad/r/ad_ou"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # path - (optional) is a type of string
  path = null
  # protected - (optional) is a type of bool
  protected = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Description of the OU."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Name of the OU."
  type        = string
}

variable "path" {
  description = "(optional) - DN of the object that contains the OU."
  type        = string
  default     = null
}

variable "protected" {
  description = "(optional) - Protect this OU from being deleted accidentaly."
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "ad_ou" "this" {
  description = var.description
  name        = var.name
  path        = var.path
  protected   = var.protected
}
```

[top](#index)

### Outputs

```terraform
output "dn" {
  description = "returns a string"
  value       = ad_ou.this.dn
}

output "guid" {
  description = "returns a string"
  value       = ad_ou.this.guid
}

output "id" {
  description = "returns a string"
  value       = ad_ou.this.id
}

output "this" {
  value = ad_ou.this
}
```

[top](#index)