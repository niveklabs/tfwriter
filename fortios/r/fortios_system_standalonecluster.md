# fortios_system_standalonecluster

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_system_standalonecluster" {
  source = "./modules/fortios/r/fortios_system_standalonecluster"

  # encryption - (optional) is a type of string
  encryption = null
  # group_member_id - (optional) is a type of number
  group_member_id = null
  # layer2_connection - (optional) is a type of string
  layer2_connection = null
  # psksecret - (optional) is a type of string
  psksecret = null
  # session_sync_dev - (optional) is a type of string
  session_sync_dev = null
  # standalone_group_id - (optional) is a type of number
  standalone_group_id = null
}
```

[top](#index)

### Variables

```terraform
variable "encryption" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group_member_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "layer2_connection" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "psksecret" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "session_sync_dev" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "standalone_group_id" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_standalonecluster" "this" {
  encryption          = var.encryption
  group_member_id     = var.group_member_id
  layer2_connection   = var.layer2_connection
  psksecret           = var.psksecret
  session_sync_dev    = var.session_sync_dev
  standalone_group_id = var.standalone_group_id
}
```

[top](#index)

### Outputs

```terraform
output "encryption" {
  description = "returns a string"
  value       = fortios_system_standalonecluster.this.encryption
}

output "group_member_id" {
  description = "returns a number"
  value       = fortios_system_standalonecluster.this.group_member_id
}

output "id" {
  description = "returns a string"
  value       = fortios_system_standalonecluster.this.id
}

output "layer2_connection" {
  description = "returns a string"
  value       = fortios_system_standalonecluster.this.layer2_connection
}

output "session_sync_dev" {
  description = "returns a string"
  value       = fortios_system_standalonecluster.this.session_sync_dev
}

output "standalone_group_id" {
  description = "returns a number"
  value       = fortios_system_standalonecluster.this.standalone_group_id
}

output "this" {
  value = fortios_system_standalonecluster.this
}
```

[top](#index)