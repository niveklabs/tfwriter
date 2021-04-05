# prismacloud_compliance_standard

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
    prismacloud = ">= 1.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "prismacloud_compliance_standard" {
  source = "./modules/prismacloud/d/prismacloud_compliance_standard"

  # cs_id - (optional) is a type of string
  cs_id = null
  # name - (optional) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "cs_id" {
  description = "(optional) - Compliance standard ID"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - Compliance standard name"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "prismacloud_compliance_standard" "this" {
  cs_id = var.cs_id
  name  = var.name
}
```

[top](#index)

### Outputs

```terraform
output "cloud_types" {
  description = "returns a list of string"
  value       = data.prismacloud_compliance_standard.this.cloud_types
}

output "created_by" {
  description = "returns a string"
  value       = data.prismacloud_compliance_standard.this.created_by
}

output "created_on" {
  description = "returns a number"
  value       = data.prismacloud_compliance_standard.this.created_on
}

output "cs_id" {
  description = "returns a string"
  value       = data.prismacloud_compliance_standard.this.cs_id
}

output "description" {
  description = "returns a string"
  value       = data.prismacloud_compliance_standard.this.description
}

output "id" {
  description = "returns a string"
  value       = data.prismacloud_compliance_standard.this.id
}

output "last_modified_by" {
  description = "returns a string"
  value       = data.prismacloud_compliance_standard.this.last_modified_by
}

output "last_modified_on" {
  description = "returns a number"
  value       = data.prismacloud_compliance_standard.this.last_modified_on
}

output "name" {
  description = "returns a string"
  value       = data.prismacloud_compliance_standard.this.name
}

output "policies_assigned_count" {
  description = "returns a number"
  value       = data.prismacloud_compliance_standard.this.policies_assigned_count
}

output "system_default" {
  description = "returns a bool"
  value       = data.prismacloud_compliance_standard.this.system_default
}

output "this" {
  value = prismacloud_compliance_standard.this
}
```

[top](#index)