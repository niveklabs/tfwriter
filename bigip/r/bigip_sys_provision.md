# bigip_sys_provision

[back](../bigip.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    bigip = ">= 1.8.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "bigip_sys_provision" {
  source = "./modules/bigip/r/bigip_sys_provision"

  # cpu_ratio - (optional) is a type of number
  cpu_ratio = null
  # disk_ratio - (optional) is a type of number
  disk_ratio = null
  # full_path - (optional) is a type of string
  full_path = null
  # level - (optional) is a type of string
  level = null
  # memory_ratio - (optional) is a type of number
  memory_ratio = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "cpu_ratio" {
  description = "(optional) - cpu Ratio"
  type        = number
  default     = null
}

variable "disk_ratio" {
  description = "(optional) - disk Ratio"
  type        = number
  default     = null
}

variable "full_path" {
  description = "(optional) - path"
  type        = string
  default     = null
}

variable "level" {
  description = "(optional) - what level nominal or dedicated"
  type        = string
  default     = null
}

variable "memory_ratio" {
  description = "(optional) - memory Ratio"
  type        = number
  default     = null
}

variable "name" {
  description = "(required) - Name of the module to be provisioned"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "bigip_sys_provision" "this" {
  # cpu_ratio - (optional) is a type of number
  cpu_ratio = var.cpu_ratio
  # disk_ratio - (optional) is a type of number
  disk_ratio = var.disk_ratio
  # full_path - (optional) is a type of string
  full_path = var.full_path
  # level - (optional) is a type of string
  level = var.level
  # memory_ratio - (optional) is a type of number
  memory_ratio = var.memory_ratio
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "full_path" {
  description = "returns a string"
  value       = bigip_sys_provision.this.full_path
}

output "id" {
  description = "returns a string"
  value       = bigip_sys_provision.this.id
}

output "this" {
  value = bigip_sys_provision.this
}
```

[top](#index)