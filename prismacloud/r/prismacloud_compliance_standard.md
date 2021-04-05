# prismacloud_compliance_standard

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
module "prismacloud_compliance_standard" {
  source = "./modules/prismacloud/r/prismacloud_compliance_standard"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Description"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Compliance standard name"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "prismacloud_compliance_standard" "this" {
  description = var.description
  name        = var.name
}
```

[top](#index)

### Outputs

```terraform
output "cloud_types" {
  description = "returns a list of string"
  value       = prismacloud_compliance_standard.this.cloud_types
}

output "created_by" {
  description = "returns a string"
  value       = prismacloud_compliance_standard.this.created_by
}

output "created_on" {
  description = "returns a number"
  value       = prismacloud_compliance_standard.this.created_on
}

output "cs_id" {
  description = "returns a string"
  value       = prismacloud_compliance_standard.this.cs_id
}

output "id" {
  description = "returns a string"
  value       = prismacloud_compliance_standard.this.id
}

output "last_modified_by" {
  description = "returns a string"
  value       = prismacloud_compliance_standard.this.last_modified_by
}

output "last_modified_on" {
  description = "returns a number"
  value       = prismacloud_compliance_standard.this.last_modified_on
}

output "policies_assigned_count" {
  description = "returns a number"
  value       = prismacloud_compliance_standard.this.policies_assigned_count
}

output "system_default" {
  description = "returns a bool"
  value       = prismacloud_compliance_standard.this.system_default
}

output "this" {
  value = prismacloud_compliance_standard.this
}
```

[top](#index)