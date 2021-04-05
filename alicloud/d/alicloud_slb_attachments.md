# alicloud_slb_attachments

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
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_slb_attachments" {
  source = "./modules/alicloud/d/alicloud_slb_attachments"

  # instance_ids - (optional) is a type of list of string
  instance_ids = []
  # load_balancer_id - (required) is a type of string
  load_balancer_id = null
  # output_file - (optional) is a type of string
  output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "instance_ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "load_balancer_id" {
  description = "(required)"
  type        = string
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_slb_attachments" "this" {
  instance_ids     = var.instance_ids
  load_balancer_id = var.load_balancer_id
  output_file      = var.output_file
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_slb_attachments.this.id
}

output "slb_attachments" {
  description = "returns a list of object"
  value       = data.alicloud_slb_attachments.this.slb_attachments
}

output "this" {
  value = alicloud_slb_attachments.this
}
```

[top](#index)