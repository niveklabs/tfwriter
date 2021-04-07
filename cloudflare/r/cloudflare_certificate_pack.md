# cloudflare_certificate_pack

[back](../cloudflare.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    cloudflare = ">= 2.19.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "cloudflare_certificate_pack" {
  source = "./modules/cloudflare/r/cloudflare_certificate_pack"

  # certificate_authority - (optional) is a type of string
  certificate_authority = null
  # cloudflare_branding - (optional) is a type of bool
  cloudflare_branding = null
  # hosts - (required) is a type of set of string
  hosts = []
  # type - (required) is a type of string
  type = null
  # validation_method - (optional) is a type of string
  validation_method = null
  # validity_days - (optional) is a type of number
  validity_days = null
  # zone_id - (required) is a type of string
  zone_id = null
}
```

[top](#index)

### Variables

```terraform
variable "certificate_authority" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cloudflare_branding" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "hosts" {
  description = "(required)"
  type        = set(string)
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "validation_method" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "validity_days" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "zone_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "cloudflare_certificate_pack" "this" {
  # certificate_authority - (optional) is a type of string
  certificate_authority = var.certificate_authority
  # cloudflare_branding - (optional) is a type of bool
  cloudflare_branding = var.cloudflare_branding
  # hosts - (required) is a type of set of string
  hosts = var.hosts
  # type - (required) is a type of string
  type = var.type
  # validation_method - (optional) is a type of string
  validation_method = var.validation_method
  # validity_days - (optional) is a type of number
  validity_days = var.validity_days
  # zone_id - (required) is a type of string
  zone_id = var.zone_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = cloudflare_certificate_pack.this.id
}

output "this" {
  value = cloudflare_certificate_pack.this
}
```

[top](#index)