# tencentcloud_tcr_instance

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tencentcloud = ">= 1.56.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tencentcloud_tcr_instance" {
  source = "./modules/tencentcloud/r/tencentcloud_tcr_instance"

  # delete_bucket - (optional) is a type of bool
  delete_bucket = null
  # instance_type - (required) is a type of string
  instance_type = null
  # name - (required) is a type of string
  name = null
  # open_public_operation - (optional) is a type of bool
  open_public_operation = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "delete_bucket" {
  description = "(optional) - Indicate to delete the COS bucket which is auto-created with the instance or not."
  type        = bool
  default     = null
}

variable "instance_type" {
  description = "(required) - TCR types. Valid values are: `standard`, `basic`, `premium`."
  type        = string
}

variable "name" {
  description = "(required) - Name of the TCR instance."
  type        = string
}

variable "open_public_operation" {
  description = "(optional) - Control public network access."
  type        = bool
  default     = null
}

variable "tags" {
  description = "(optional) - The available tags within this TCR instance."
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_tcr_instance" "this" {
  delete_bucket         = var.delete_bucket
  instance_type         = var.instance_type
  name                  = var.name
  open_public_operation = var.open_public_operation
  tags                  = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_tcr_instance.this.id
}

output "internal_end_point" {
  description = "returns a string"
  value       = tencentcloud_tcr_instance.this.internal_end_point
}

output "public_domain" {
  description = "returns a string"
  value       = tencentcloud_tcr_instance.this.public_domain
}

output "public_status" {
  description = "returns a string"
  value       = tencentcloud_tcr_instance.this.public_status
}

output "status" {
  description = "returns a string"
  value       = tencentcloud_tcr_instance.this.status
}

output "this" {
  value = tencentcloud_tcr_instance.this
}
```

[top](#index)