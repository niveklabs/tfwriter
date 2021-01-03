# prismacloud_compliance_standard_requirement_section

[back](../prismacloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/prismacloud/d/prismacloud_compliance_standard_requirement_section"

  # csr_id - (required) is a type of string
  csr_id = null
  # csrs_id - (optional) is a type of string
  csrs_id = null
  # section_id - (optional) is a type of string
  section_id = null
}
```

[top](#index)

### Variables

```terraform
variable "csr_id" {
  description = "(required) - Compliance standard requirement ID"
  type        = string
}

variable "csrs_id" {
  description = "(optional) - Compliance standard requirement section ID"
  type        = string
  default     = null
}

variable "section_id" {
  description = "(optional) - Compliance section ID"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "prismacloud_compliance_standard_requirement_section" "this" {
  csr_id     = var.csr_id
  csrs_id    = var.csrs_id
  section_id = var.section_id
}
```

[top](#index)

### Outputs

```terraform
output "associated_policy_ids" {
  description = "returns a list of string"
  value       = data.prismacloud_compliance_standard_requirement_section.this.associated_policy_ids
}

output "created_by" {
  description = "returns a string"
  value       = data.prismacloud_compliance_standard_requirement_section.this.created_by
}

output "created_on" {
  description = "returns a number"
  value       = data.prismacloud_compliance_standard_requirement_section.this.created_on
}

output "csrs_id" {
  description = "returns a string"
  value       = data.prismacloud_compliance_standard_requirement_section.this.csrs_id
}

output "description" {
  description = "returns a string"
  value       = data.prismacloud_compliance_standard_requirement_section.this.description
}

output "id" {
  description = "returns a string"
  value       = data.prismacloud_compliance_standard_requirement_section.this.id
}

output "label" {
  description = "returns a string"
  value       = data.prismacloud_compliance_standard_requirement_section.this.label
}

output "last_modified_by" {
  description = "returns a string"
  value       = data.prismacloud_compliance_standard_requirement_section.this.last_modified_by
}

output "last_modified_on" {
  description = "returns a number"
  value       = data.prismacloud_compliance_standard_requirement_section.this.last_modified_on
}

output "policies_assigned_count" {
  description = "returns a number"
  value       = data.prismacloud_compliance_standard_requirement_section.this.policies_assigned_count
}

output "requirement_name" {
  description = "returns a string"
  value       = data.prismacloud_compliance_standard_requirement_section.this.requirement_name
}

output "section_count" {
  description = "returns a number"
  value       = data.prismacloud_compliance_standard_requirement_section.this.section_count
}

output "section_id" {
  description = "returns a string"
  value       = data.prismacloud_compliance_standard_requirement_section.this.section_id
}

output "standard_name" {
  description = "returns a string"
  value       = data.prismacloud_compliance_standard_requirement_section.this.standard_name
}

output "system_default" {
  description = "returns a bool"
  value       = data.prismacloud_compliance_standard_requirement_section.this.system_default
}

output "view_order" {
  description = "returns a number"
  value       = data.prismacloud_compliance_standard_requirement_section.this.view_order
}

output "this" {
  value = prismacloud_compliance_standard_requirement_section.this
}
```

[top](#index)