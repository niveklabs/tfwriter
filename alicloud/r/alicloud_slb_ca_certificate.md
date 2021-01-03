# alicloud_slb_ca_certificate

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
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_slb_ca_certificate" {
  source = "./modules/alicloud/r/alicloud_slb_ca_certificate"

  # ca_certificate - (required) is a type of string
  ca_certificate = null
  # name - (optional) is a type of string
  name = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "ca_certificate" {
  description = "(required)"
  type        = string
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

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_slb_ca_certificate" "this" {
  ca_certificate    = var.ca_certificate
  name              = var.name
  resource_group_id = var.resource_group_id
  tags              = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_slb_ca_certificate.this.id
}

output "resource_group_id" {
  description = "returns a string"
  value       = alicloud_slb_ca_certificate.this.resource_group_id
}

output "this" {
  value = alicloud_slb_ca_certificate.this
}
```

[top](#index)