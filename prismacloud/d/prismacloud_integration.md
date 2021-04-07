# prismacloud_integration

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
module "prismacloud_integration" {
  source = "./modules/prismacloud/d/prismacloud_integration"

  # integration_id - (optional) is a type of string
  integration_id = null
  # name - (optional) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "integration_id" {
  description = "(optional) - Integration ID"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - Name of the integration"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "prismacloud_integration" "this" {
  # integration_id - (optional) is a type of string
  integration_id = var.integration_id
  # name - (optional) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "created_by" {
  description = "returns a string"
  value       = data.prismacloud_integration.this.created_by
}

output "created_ts" {
  description = "returns a number"
  value       = data.prismacloud_integration.this.created_ts
}

output "description" {
  description = "returns a string"
  value       = data.prismacloud_integration.this.description
}

output "enabled" {
  description = "returns a bool"
  value       = data.prismacloud_integration.this.enabled
}

output "id" {
  description = "returns a string"
  value       = data.prismacloud_integration.this.id
}

output "integration_config" {
  description = "returns a list of object"
  value       = data.prismacloud_integration.this.integration_config
}

output "integration_id" {
  description = "returns a string"
  value       = data.prismacloud_integration.this.integration_id
}

output "integration_type" {
  description = "returns a string"
  value       = data.prismacloud_integration.this.integration_type
}

output "last_modified_by" {
  description = "returns a string"
  value       = data.prismacloud_integration.this.last_modified_by
}

output "last_modified_ts" {
  description = "returns a number"
  value       = data.prismacloud_integration.this.last_modified_ts
}

output "name" {
  description = "returns a string"
  value       = data.prismacloud_integration.this.name
}

output "reason" {
  description = "returns a list of object"
  value       = data.prismacloud_integration.this.reason
}

output "status" {
  description = "returns a string"
  value       = data.prismacloud_integration.this.status
}

output "valid" {
  description = "returns a bool"
  value       = data.prismacloud_integration.this.valid
}

output "this" {
  value = prismacloud_integration.this
}
```

[top](#index)