# alicloud_cen_instance_attachments

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
module "alicloud_cen_instance_attachments" {
  source = "./modules/alicloud/d/alicloud_cen_instance_attachments"

  # child_instance_region_id - (optional) is a type of string
  child_instance_region_id = null
  # child_instance_type - (optional) is a type of string
  child_instance_type = null
  # instance_id - (required) is a type of string
  instance_id = null
  # output_file - (optional) is a type of string
  output_file = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "child_instance_region_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "child_instance_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_id" {
  description = "(required)"
  type        = string
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_cen_instance_attachments" "this" {
  child_instance_region_id = var.child_instance_region_id
  child_instance_type      = var.child_instance_type
  instance_id              = var.instance_id
  output_file              = var.output_file
  status                   = var.status
}
```

[top](#index)

### Outputs

```terraform
output "attachments" {
  description = "returns a list of object"
  value       = data.alicloud_cen_instance_attachments.this.attachments
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_cen_instance_attachments.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_cen_instance_attachments.this.ids
}

output "this" {
  value = alicloud_cen_instance_attachments.this
}
```

[top](#index)