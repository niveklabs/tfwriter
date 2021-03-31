# alicloud_dns

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
module "alicloud_dns" {
  source = "./modules/alicloud/r/alicloud_dns"

  # group_id - (optional) is a type of string
  group_id = null
  # name - (required) is a type of string
  name = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
}
```

[top](#index)

### Variables

```terraform
variable "group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_dns" "this" {
  group_id          = var.group_id
  name              = var.name
  resource_group_id = var.resource_group_id
}
```

[top](#index)

### Outputs

```terraform
output "dns_server" {
  description = "returns a set of string"
  value       = alicloud_dns.this.dns_server
}

output "domain_id" {
  description = "returns a string"
  value       = alicloud_dns.this.domain_id
}

output "id" {
  description = "returns a string"
  value       = alicloud_dns.this.id
}

output "this" {
  value = alicloud_dns.this
}
```

[top](#index)