# aci_vpc_explicit_protection_group

[back](../aci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/aci/d/aci_vpc_explicit_protection_group"

  # annotation - (optional) is a type of string
  annotation = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
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

variable "vpc_explicit_protection_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aci_vpc_explicit_protection_group" "this" {
  # annotation - (optional) is a type of string
  annotation = var.annotation
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # vpc_explicit_protection_group_id - (optional) is a type of string
  vpc_explicit_protection_group_id = var.vpc_explicit_protection_group_id
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.aci_vpc_explicit_protection_group.this.description
}

output "id" {
  description = "returns a string"
  value       = data.aci_vpc_explicit_protection_group.this.id
}

output "vpc_explicit_protection_group_id" {
  description = "returns a string"
  value       = data.aci_vpc_explicit_protection_group.this.vpc_explicit_protection_group_id
}

output "this" {
  value = aci_vpc_explicit_protection_group.this
}
```

[top](#index)