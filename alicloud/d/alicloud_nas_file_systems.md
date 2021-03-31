# alicloud_nas_file_systems

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "alicloud_nas_file_systems" {
  source = "./modules/alicloud/d/alicloud_nas_file_systems"

  # description_regex - (optional) is a type of string
  description_regex = null
  # ids - (optional) is a type of list of string
  ids = []
  # output_file - (optional) is a type of string
  output_file = null
  # protocol_type - (optional) is a type of string
  protocol_type = null
  # storage_type - (optional) is a type of string
  storage_type = null
}
```

[top](#index)

### Variables

```terraform
variable "description_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "protocol_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "storage_type" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_nas_file_systems" "this" {
  description_regex = var.description_regex
  ids               = var.ids
  output_file       = var.output_file
  protocol_type     = var.protocol_type
  storage_type      = var.storage_type
}
```

[top](#index)

### Outputs

```terraform
output "descriptions" {
  description = "returns a list of string"
  value       = data.alicloud_nas_file_systems.this.descriptions
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_nas_file_systems.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_nas_file_systems.this.ids
}

output "systems" {
  description = "returns a list of object"
  value       = data.alicloud_nas_file_systems.this.systems
}

output "this" {
  value = alicloud_nas_file_systems.this
}
```

[top](#index)