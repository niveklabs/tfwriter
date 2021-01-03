# alicloud_eip_association

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
module "alicloud_eip_association" {
  source = "./modules/alicloud/r/alicloud_eip_association"

  # allocation_id - (required) is a type of string
  allocation_id = null
  # force - (optional) is a type of bool
  force = null
  # instance_id - (required) is a type of string
  instance_id = null
  # instance_type - (optional) is a type of string
  instance_type = null
  # private_ip_address - (optional) is a type of string
  private_ip_address = null
}
```

[top](#index)

### Variables

```terraform
variable "allocation_id" {
  description = "(required)"
  type        = string
}

variable "force" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "instance_id" {
  description = "(required)"
  type        = string
}

variable "instance_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "private_ip_address" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_eip_association" "this" {
  allocation_id      = var.allocation_id
  force              = var.force
  instance_id        = var.instance_id
  instance_type      = var.instance_type
  private_ip_address = var.private_ip_address
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_eip_association.this.id
}

output "instance_type" {
  description = "returns a string"
  value       = alicloud_eip_association.this.instance_type
}

output "private_ip_address" {
  description = "returns a string"
  value       = alicloud_eip_association.this.private_ip_address
}

output "this" {
  value = alicloud_eip_association.this
}
```

[top](#index)