# aci_span_sourcedestination_group_match_label

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
module "aci_span_sourcedestination_group_match_label" {
  source = "./modules/aci/r/aci_span_sourcedestination_group_match_label"

  # annotation - (optional) is a type of string
  annotation = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # span_source_group_dn - (required) is a type of string
  span_source_group_dn = null
  # tag - (optional) is a type of string
  tag = null
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

variable "name_alias" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "span_source_group_dn" {
  description = "(required)"
  type        = string
}

variable "tag" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aci_span_sourcedestination_group_match_label" "this" {
  annotation           = var.annotation
  description          = var.description
  name                 = var.name
  name_alias           = var.name_alias
  span_source_group_dn = var.span_source_group_dn
  tag                  = var.tag
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = aci_span_sourcedestination_group_match_label.this.description
}

output "id" {
  description = "returns a string"
  value       = aci_span_sourcedestination_group_match_label.this.id
}

output "name_alias" {
  description = "returns a string"
  value       = aci_span_sourcedestination_group_match_label.this.name_alias
}

output "tag" {
  description = "returns a string"
  value       = aci_span_sourcedestination_group_match_label.this.tag
}

output "this" {
  value = aci_span_sourcedestination_group_match_label.this
}
```

[top](#index)