# alicloud_ram_role

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_ram_role" {
  source = "./modules/alicloud/r/alicloud_ram_role"

  # description - (optional) is a type of string
  description = null
  # document - (optional) is a type of string
  document = null
  # force - (optional) is a type of bool
  force = null
  # max_session_duration - (optional) is a type of number
  max_session_duration = null
  # name - (required) is a type of string
  name = null
  # ram_users - (optional) is a type of set of string
  ram_users = []
  # services - (optional) is a type of set of string
  services = []
  # version - (optional) is a type of string
  version = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "document" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "force" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "max_session_duration" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "ram_users" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "services" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "version" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_ram_role" "this" {
  description          = var.description
  document             = var.document
  force                = var.force
  max_session_duration = var.max_session_duration
  name                 = var.name
  ram_users            = var.ram_users
  services             = var.services
  version              = var.version
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = alicloud_ram_role.this.arn
}

output "document" {
  description = "returns a string"
  value       = alicloud_ram_role.this.document
}

output "id" {
  description = "returns a string"
  value       = alicloud_ram_role.this.id
}

output "ram_users" {
  description = "returns a set of string"
  value       = alicloud_ram_role.this.ram_users
}

output "role_id" {
  description = "returns a string"
  value       = alicloud_ram_role.this.role_id
}

output "services" {
  description = "returns a set of string"
  value       = alicloud_ram_role.this.services
}

output "this" {
  value = alicloud_ram_role.this
}
```

[top](#index)