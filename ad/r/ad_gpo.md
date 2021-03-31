# ad_gpo

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
module "ad_gpo" {
  source = "./modules/ad/r/ad_gpo"

  # description - (optional) is a type of string
  description = null
  # domain - (optional) is a type of string
  domain = null
  # name - (required) is a type of string
  name = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Description of the GPO."
  type        = string
  default     = null
}

variable "domain" {
  description = "(optional) - Domain of the GPO."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Name of the GPO."
  type        = string
}

variable "status" {
  description = "(optional) - Status of the GPO. Can be one of `AllSettingsEnabled`, `UserSettingsDisabled`, `ComputerSettingsDisabled`, or `AllSettingsDisabled` (case sensitive)."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "ad_gpo" "this" {
  description = var.description
  domain      = var.domain
  name        = var.name
  status      = var.status
}
```

[top](#index)

### Outputs

```terraform
output "dn" {
  description = "returns a string"
  value       = ad_gpo.this.dn
}

output "id" {
  description = "returns a string"
  value       = ad_gpo.this.id
}

output "numeric_status" {
  description = "returns a number"
  value       = ad_gpo.this.numeric_status
}

output "this" {
  value = ad_gpo.this
}
```

[top](#index)