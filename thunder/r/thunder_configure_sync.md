# thunder_configure_sync

[back](../thunder.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    thunder = ">= 0.4.16"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "thunder_configure_sync" {
  source = "./modules/thunder/r/thunder_configure_sync"

  # address - (optional) is a type of string
  address = null
  # all_partitions - (optional) is a type of number
  all_partitions = null
  # auto_authentication - (optional) is a type of number
  auto_authentication = null
  # partition_name - (optional) is a type of string
  partition_name = null
  # private_key - (optional) is a type of string
  private_key = null
  # pwd - (optional) is a type of string
  pwd = null
  # pwd_enc - (optional) is a type of string
  pwd_enc = null
  # shared - (optional) is a type of number
  shared = null
  # type - (optional) is a type of string
  type = null
  # usr - (optional) is a type of string
  usr = null
}
```

[top](#index)

### Variables

```terraform
variable "address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "all_partitions" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "auto_authentication" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "partition_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "private_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pwd" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pwd_enc" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "shared" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "usr" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "thunder_configure_sync" "this" {
  # address - (optional) is a type of string
  address = var.address
  # all_partitions - (optional) is a type of number
  all_partitions = var.all_partitions
  # auto_authentication - (optional) is a type of number
  auto_authentication = var.auto_authentication
  # partition_name - (optional) is a type of string
  partition_name = var.partition_name
  # private_key - (optional) is a type of string
  private_key = var.private_key
  # pwd - (optional) is a type of string
  pwd = var.pwd
  # pwd_enc - (optional) is a type of string
  pwd_enc = var.pwd_enc
  # shared - (optional) is a type of number
  shared = var.shared
  # type - (optional) is a type of string
  type = var.type
  # usr - (optional) is a type of string
  usr = var.usr
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_configure_sync.this.id
}

output "this" {
  value = thunder_configure_sync.this
}
```

[top](#index)