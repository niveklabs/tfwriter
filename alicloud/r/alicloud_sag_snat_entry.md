# alicloud_sag_snat_entry

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
module "alicloud_sag_snat_entry" {
  source = "./modules/alicloud/r/alicloud_sag_snat_entry"

  # cidr_block - (required) is a type of string
  cidr_block = null
  # sag_id - (required) is a type of string
  sag_id = null
  # snat_ip - (required) is a type of string
  snat_ip = null
}
```

[top](#index)

### Variables

```terraform
variable "cidr_block" {
  description = "(required)"
  type        = string
}

variable "sag_id" {
  description = "(required)"
  type        = string
}

variable "snat_ip" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_sag_snat_entry" "this" {
  cidr_block = var.cidr_block
  sag_id     = var.sag_id
  snat_ip    = var.snat_ip
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_sag_snat_entry.this.id
}

output "this" {
  value = alicloud_sag_snat_entry.this
}
```

[top](#index)