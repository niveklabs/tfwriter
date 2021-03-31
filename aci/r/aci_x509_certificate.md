# aci_x509_certificate

[back](../aci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aci = ">= 0.5.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aci_x509_certificate" {
  source = "./modules/aci/r/aci_x509_certificate"

  # annotation - (optional) is a type of string
  annotation = null
  # data - (optional) is a type of string
  data = null
  # description - (optional) is a type of string
  description = null
  # local_user_dn - (required) is a type of string
  local_user_dn = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
}
```

[top](#index)

### Variables

```terraform
variable "annotation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "data" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "local_user_dn" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "name_alias" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aci_x509_certificate" "this" {
  annotation    = var.annotation
  data          = var.data
  description   = var.description
  local_user_dn = var.local_user_dn
  name          = var.name
  name_alias    = var.name_alias
}
```

[top](#index)

### Outputs

```terraform
output "data" {
  description = "returns a string"
  value       = aci_x509_certificate.this.data
}

output "description" {
  description = "returns a string"
  value       = aci_x509_certificate.this.description
}

output "id" {
  description = "returns a string"
  value       = aci_x509_certificate.this.id
}

output "name_alias" {
  description = "returns a string"
  value       = aci_x509_certificate.this.name_alias
}

output "this" {
  value = aci_x509_certificate.this
}
```

[top](#index)