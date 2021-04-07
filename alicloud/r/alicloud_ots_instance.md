# alicloud_ots_instance

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
module "alicloud_ots_instance" {
  source = "./modules/alicloud/r/alicloud_ots_instance"

  # accessed_by - (optional) is a type of string
  accessed_by = null
  # description - (optional) is a type of string
  description = null
  # instance_type - (optional) is a type of string
  instance_type = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "accessed_by" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_ots_instance" "this" {
  # accessed_by - (optional) is a type of string
  accessed_by = var.accessed_by
  # description - (optional) is a type of string
  description = var.description
  # instance_type - (optional) is a type of string
  instance_type = var.instance_type
  # name - (required) is a type of string
  name = var.name
  # tags - (optional) is a type of map of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_ots_instance.this.id
}

output "this" {
  value = alicloud_ots_instance.this
}
```

[top](#index)