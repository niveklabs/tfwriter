# prismacloud_compliance_standard_requirement

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
    prismacloud = ">= 1.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "prismacloud_compliance_standard_requirement" {
  source = "./modules/prismacloud/r/prismacloud_compliance_standard_requirement"

  # cs_id - (required) is a type of string
  cs_id = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # requirement_id - (optional) is a type of string
  requirement_id = null
  # view_order - (optional) is a type of number
  view_order = null
}
```

[top](#index)

### Variables

```terraform
variable "cs_id" {
  description = "(required) - Compliance standard ID"
  type        = string
}

variable "description" {
  description = "(optional) - Description"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Compliance requirement name"
  type        = string
}

variable "requirement_id" {
  description = "(optional) - Compliance requirement number"
  type        = string
  default     = null
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
resource "prismacloud_compliance_standard_requirement" "this" {
  cs_id          = var.cs_id
  description    = var.description
  name           = var.name
  requirement_id = var.requirement_id
  view_order     = var.view_order
}
```

[top](#index)

### Outputs

```terraform
output "created_by" {
  description = "returns a string"
  value       = prismacloud_compliance_standard_requirement.this.created_by
}

output "created_on" {
  description = "returns a number"
  value       = prismacloud_compliance_standard_requirement.this.created_on
}

output "csr_id" {
  description = "returns a string"
  value       = prismacloud_compliance_standard_requirement.this.csr_id
}

output "id" {
  description = "returns a string"
  value       = prismacloud_compliance_standard_requirement.this.id
}

output "last_modified_by" {
  description = "returns a string"
  value       = prismacloud_compliance_standard_requirement.this.last_modified_by
}

output "last_modified_on" {
  description = "returns a number"
  value       = prismacloud_compliance_standard_requirement.this.last_modified_on
}

output "policies_assigned_count" {
  description = "returns a number"
  value       = prismacloud_compliance_standard_requirement.this.policies_assigned_count
}

output "standard_name" {
  description = "returns a string"
  value       = prismacloud_compliance_standard_requirement.this.standard_name
}

output "system_default" {
  description = "returns a bool"
  value       = prismacloud_compliance_standard_requirement.this.system_default
}

output "view_order" {
  description = "returns a number"
  value       = prismacloud_compliance_standard_requirement.this.view_order
}

output "this" {
  value = prismacloud_compliance_standard_requirement.this
}
```

[top](#index)