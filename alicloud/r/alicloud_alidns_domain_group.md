# alicloud_alidns_domain_group

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
module "alicloud_alidns_domain_group" {
  source = "./modules/alicloud/r/alicloud_alidns_domain_group"

  # domain_group_name - (optional) is a type of string
  domain_group_name = null
  # group_name - (optional) is a type of string
  group_name = null
  # lang - (optional) is a type of string
  lang = null
}
```

[top](#index)

### Variables

```terraform
variable "domain_group_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "lang" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_alidns_domain_group" "this" {
  domain_group_name = var.domain_group_name
  group_name        = var.group_name
  lang              = var.lang
}
```

[top](#index)

### Outputs

```terraform
output "domain_group_name" {
  description = "returns a string"
  value       = alicloud_alidns_domain_group.this.domain_group_name
}

output "group_name" {
  description = "returns a string"
  value       = alicloud_alidns_domain_group.this.group_name
}

output "id" {
  description = "returns a string"
  value       = alicloud_alidns_domain_group.this.id
}

output "this" {
  value = alicloud_alidns_domain_group.this
}
```

[top](#index)