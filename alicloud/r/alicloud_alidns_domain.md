# alicloud_alidns_domain

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
module "alicloud_alidns_domain" {
  source = "./modules/alicloud/r/alicloud_alidns_domain"

  # domain_name - (required) is a type of string
  domain_name = null
  # group_id - (optional) is a type of string
  group_id = null
  # lang - (optional) is a type of string
  lang = null
  # remark - (optional) is a type of string
  remark = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # tags - (optional) is a type of map of string
  tags = {}

  timeouts = [{
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "domain_name" {
  description = "(required)"
  type        = string
}

variable "group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "lang" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "remark" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_alidns_domain" "this" {
  # domain_name - (required) is a type of string
  domain_name = var.domain_name
  # group_id - (optional) is a type of string
  group_id = var.group_id
  # lang - (optional) is a type of string
  lang = var.lang
  # remark - (optional) is a type of string
  remark = var.remark
  # resource_group_id - (optional) is a type of string
  resource_group_id = var.resource_group_id
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "dns_servers" {
  description = "returns a set of string"
  value       = alicloud_alidns_domain.this.dns_servers
}

output "domain_id" {
  description = "returns a string"
  value       = alicloud_alidns_domain.this.domain_id
}

output "group_name" {
  description = "returns a string"
  value       = alicloud_alidns_domain.this.group_name
}

output "id" {
  description = "returns a string"
  value       = alicloud_alidns_domain.this.id
}

output "puny_code" {
  description = "returns a string"
  value       = alicloud_alidns_domain.this.puny_code
}

output "resource_group_id" {
  description = "returns a string"
  value       = alicloud_alidns_domain.this.resource_group_id
}

output "this" {
  value = alicloud_alidns_domain.this
}
```

[top](#index)