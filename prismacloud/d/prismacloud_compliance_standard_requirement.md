# prismacloud_compliance_standard_requirement

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
module "prismacloud_compliance_standard_requirement" {
  source = "./modules/prismacloud/d/prismacloud_compliance_standard_requirement"

  # cs_id - (required) is a type of string
  cs_id = null
  # csr_id - (optional) is a type of string
  csr_id = null
  # name - (optional) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "cs_id" {
  description = "(required) - Compliance standard ID"
  type        = string
}

variable "csr_id" {
  description = "(optional) - Compliance standard requirement ID"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - Compliance requirement name"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "prismacloud_compliance_standard_requirement" "this" {
  cs_id  = var.cs_id
  csr_id = var.csr_id
  name   = var.name
}
```

[top](#index)

### Outputs

```terraform
output "created_by" {
  description = "returns a string"
  value       = data.prismacloud_compliance_standard_requirement.this.created_by
}

output "created_on" {
  description = "returns a number"
  value       = data.prismacloud_compliance_standard_requirement.this.created_on
}

output "csr_id" {
  description = "returns a string"
  value       = data.prismacloud_compliance_standard_requirement.this.csr_id
}

output "description" {
  description = "returns a string"
  value       = data.prismacloud_compliance_standard_requirement.this.description
}

output "id" {
  description = "returns a string"
  value       = data.prismacloud_compliance_standard_requirement.this.id
}

output "last_modified_by" {
  description = "returns a string"
  value       = data.prismacloud_compliance_standard_requirement.this.last_modified_by
}

output "last_modified_on" {
  description = "returns a number"
  value       = data.prismacloud_compliance_standard_requirement.this.last_modified_on
}

output "name" {
  description = "returns a string"
  value       = data.prismacloud_compliance_standard_requirement.this.name
}

output "policies_assigned_count" {
  description = "returns a number"
  value       = data.prismacloud_compliance_standard_requirement.this.policies_assigned_count
}

output "requirement_id" {
  description = "returns a string"
  value       = data.prismacloud_compliance_standard_requirement.this.requirement_id
}

output "standard_name" {
  description = "returns a string"
  value       = data.prismacloud_compliance_standard_requirement.this.standard_name
}

output "system_default" {
  description = "returns a bool"
  value       = data.prismacloud_compliance_standard_requirement.this.system_default
}

output "view_order" {
  description = "returns a number"
  value       = data.prismacloud_compliance_standard_requirement.this.view_order
}

output "this" {
  value = prismacloud_compliance_standard_requirement.this
}
```

[top](#index)