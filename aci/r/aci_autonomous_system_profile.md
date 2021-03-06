# aci_autonomous_system_profile

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
module "aci_autonomous_system_profile" {
  source = "./modules/aci/r/aci_autonomous_system_profile"

  # annotation - (optional) is a type of string
  annotation = null
  # asn - (optional) is a type of string
  asn = null
  # description - (optional) is a type of string
  description = null
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

variable "asn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "aci_autonomous_system_profile" "this" {
  # annotation - (optional) is a type of string
  annotation = var.annotation
  # asn - (optional) is a type of string
  asn = var.asn
  # description - (optional) is a type of string
  description = var.description
  # name_alias - (optional) is a type of string
  name_alias = var.name_alias
}
```

[top](#index)

### Outputs

```terraform
output "asn" {
  description = "returns a string"
  value       = aci_autonomous_system_profile.this.asn
}

output "description" {
  description = "returns a string"
  value       = aci_autonomous_system_profile.this.description
}

output "id" {
  description = "returns a string"
  value       = aci_autonomous_system_profile.this.id
}

output "name_alias" {
  description = "returns a string"
  value       = aci_autonomous_system_profile.this.name_alias
}

output "this" {
  value = aci_autonomous_system_profile.this
}
```

[top](#index)