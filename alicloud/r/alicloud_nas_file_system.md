# alicloud_nas_file_system

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
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_nas_file_system" {
  source = "./modules/alicloud/r/alicloud_nas_file_system"

  # description - (optional) is a type of string
  description = null
  # protocol_type - (required) is a type of string
  protocol_type = null
  # storage_type - (required) is a type of string
  storage_type = null
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

variable "protocol_type" {
  description = "(required)"
  type        = string
}

variable "storage_type" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_nas_file_system" "this" {
  description   = var.description
  protocol_type = var.protocol_type
  storage_type  = var.storage_type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_nas_file_system.this.id
}

output "this" {
  value = alicloud_nas_file_system.this
}
```

[top](#index)