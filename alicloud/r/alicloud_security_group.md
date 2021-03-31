# alicloud_security_group

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
module "alicloud_security_group" {
  source = "./modules/alicloud/r/alicloud_security_group"

  # description - (optional) is a type of string
  description = null
  # inner_access - (optional) is a type of bool
  inner_access = null
  # inner_access_policy - (optional) is a type of string
  inner_access_policy = null
  # name - (optional) is a type of string
  name = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # security_group_type - (optional) is a type of string
  security_group_type = null
  # tags - (optional) is a type of map of string
  tags = {}
  # vpc_id - (optional) is a type of string
  vpc_id = null
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

variable "inner_access" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "inner_access_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_group_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "vpc_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_security_group" "this" {
  description         = var.description
  inner_access        = var.inner_access
  inner_access_policy = var.inner_access_policy
  name                = var.name
  resource_group_id   = var.resource_group_id
  security_group_type = var.security_group_type
  tags                = var.tags
  vpc_id              = var.vpc_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_security_group.this.id
}

output "inner_access" {
  description = "returns a bool"
  value       = alicloud_security_group.this.inner_access
}

output "inner_access_policy" {
  description = "returns a string"
  value       = alicloud_security_group.this.inner_access_policy
}

output "this" {
  value = alicloud_security_group.this
}
```

[top](#index)