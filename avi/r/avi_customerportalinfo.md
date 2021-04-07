# avi_customerportalinfo

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    avi = ">= 0.2.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "avi_customerportalinfo" {
  source = "./modules/avi/r/avi_customerportalinfo"

  # polling_interval - (optional) is a type of number
  polling_interval = null
  # portal_url - (optional) is a type of string
  portal_url = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "polling_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "portal_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "avi_customerportalinfo" "this" {
  # polling_interval - (optional) is a type of number
  polling_interval = var.polling_interval
  # portal_url - (optional) is a type of string
  portal_url = var.portal_url
  # uuid - (optional) is a type of string
  uuid = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = avi_customerportalinfo.this.id
}

output "portal_url" {
  description = "returns a string"
  value       = avi_customerportalinfo.this.portal_url
}

output "uuid" {
  description = "returns a string"
  value       = avi_customerportalinfo.this.uuid
}

output "this" {
  value = avi_customerportalinfo.this
}
```

[top](#index)