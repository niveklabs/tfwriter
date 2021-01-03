# prismacloud_compliance_standard_requirement_section

[back](../prismacloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    prismacloud = ">= 1.0.8"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "prismacloud_compliance_standard_requirement_section" {
  source = "./modules/prismacloud/r/prismacloud_compliance_standard_requirement_section"

  # csr_id - (required) is a type of string
  csr_id = null
  # description - (optional) is a type of string
  description = null
  # label - (optional) is a type of string
  label = null
  # section_id - (required) is a type of string
  section_id = null
  # view_order - (optional) is a type of number
  view_order = null
}
```

[top](#index)

### Variables

```terraform
variable "csr_id" {
  description = "(required) - Compliance standard requirement ID"
  type        = string
}

variable "description" {
  description = "(optional) - Description"
  type        = string
  default     = null
}

variable "label" {
  description = "(optional) - Section label"
  type        = string
  default     = null
}

variable "section_id" {
  description = "(required) - Compliance section ID"
  type        = string
}

variable "view_order" {
  description = "(optional) - View order"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "prismacloud_compliance_standard_requirement_section" "this" {
  csr_id      = var.csr_id
  description = var.description
  label       = var.label
  section_id  = var.section_id
  view_order  = var.view_order
}
```

[top](#index)

### Outputs

```terraform
output "associated_policy_ids" {
  description = "returns a list of string"
  value       = prismacloud_compliance_standard_requirement_section.this.associated_policy_ids
}

output "created_by" {
  description = "returns a string"
  value       = prismacloud_compliance_standard_requirement_section.this.created_by
}

output "created_on" {
  description = "returns a number"
  value       = prismacloud_compliance_standard_requirement_section.this.created_on
}

output "csrs_id" {
  description = "returns a string"
  value       = prismacloud_compliance_standard_requirement_section.this.csrs_id
}

output "id" {
  description = "returns a string"
  value       = prismacloud_compliance_standard_requirement_section.this.id
}

output "label" {
  description = "returns a string"
  value       = prismacloud_compliance_standard_requirement_section.this.label
}

output "last_modified_by" {
  description = "returns a string"
  value       = prismacloud_compliance_standard_requirement_section.this.last_modified_by
}

output "last_modified_on" {
  description = "returns a number"
  value       = prismacloud_compliance_standard_requirement_section.this.last_modified_on
}

output "policies_assigned_count" {
  description = "returns a number"
  value       = prismacloud_compliance_standard_requirement_section.this.policies_assigned_count
}

output "requirement_name" {
  description = "returns a string"
  value       = prismacloud_compliance_standard_requirement_section.this.requirement_name
}

output "standard_name" {
  description = "returns a string"
  value       = prismacloud_compliance_standard_requirement_section.this.standard_name
}

output "system_default" {
  description = "returns a bool"
  value       = prismacloud_compliance_standard_requirement_section.this.system_default
}

output "view_order" {
  description = "returns a number"
  value       = prismacloud_compliance_standard_requirement_section.this.view_order
}

output "this" {
  value = prismacloud_compliance_standard_requirement_section.this
}
```

[top](#index)