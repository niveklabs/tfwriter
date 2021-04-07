# aci_vpc_explicit_protection_group

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
module "aci_vpc_explicit_protection_group" {
  source = "./modules/aci/r/aci_vpc_explicit_protection_group"

  # annotation - (optional) is a type of string
  annotation = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # switch1 - (required) is a type of string
  switch1 = null
  # switch2 - (required) is a type of string
  switch2 = null
  # vpc_domain_policy - (optional) is a type of string
  vpc_domain_policy = null
  # vpc_explicit_protection_group_id - (optional) is a type of string
  vpc_explicit_protection_group_id = null
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

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "switch1" {
  description = "(required)"
  type        = string
}

variable "switch2" {
  description = "(required)"
  type        = string
}

variable "vpc_domain_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vpc_explicit_protection_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aci_vpc_explicit_protection_group" "this" {
  # annotation - (optional) is a type of string
  annotation = var.annotation
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # switch1 - (required) is a type of string
  switch1 = var.switch1
  # switch2 - (required) is a type of string
  switch2 = var.switch2
  # vpc_domain_policy - (optional) is a type of string
  vpc_domain_policy = var.vpc_domain_policy
  # vpc_explicit_protection_group_id - (optional) is a type of string
  vpc_explicit_protection_group_id = var.vpc_explicit_protection_group_id
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = aci_vpc_explicit_protection_group.this.description
}

output "id" {
  description = "returns a string"
  value       = aci_vpc_explicit_protection_group.this.id
}

output "vpc_domain_policy" {
  description = "returns a string"
  value       = aci_vpc_explicit_protection_group.this.vpc_domain_policy
}

output "vpc_explicit_protection_group_id" {
  description = "returns a string"
  value       = aci_vpc_explicit_protection_group.this.vpc_explicit_protection_group_id
}

output "this" {
  value = aci_vpc_explicit_protection_group.this
}
```

[top](#index)