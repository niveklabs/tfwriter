# alicloud_snapshots

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
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_snapshots" {
  source = "./modules/alicloud/d/alicloud_snapshots"

  # disk_id - (optional) is a type of string
  disk_id = null
  # encrypted - (optional) is a type of bool
  encrypted = null
  # ids - (optional) is a type of set of string
  ids = []
  # instance_id - (optional) is a type of string
  instance_id = null
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # source_disk_type - (optional) is a type of string
  source_disk_type = null
  # status - (optional) is a type of string
  status = null
  # tags - (optional) is a type of map of string
  tags = {}
  # type - (optional) is a type of string
  type = null
  # usage - (optional) is a type of string
  usage = null
}
```

[top](#index)

### Variables

```terraform
variable "disk_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "encrypted" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "instance_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_disk_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "usage" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_snapshots" "this" {
  disk_id          = var.disk_id
  encrypted        = var.encrypted
  ids              = var.ids
  instance_id      = var.instance_id
  name_regex       = var.name_regex
  output_file      = var.output_file
  source_disk_type = var.source_disk_type
  status           = var.status
  tags             = var.tags
  type             = var.type
  usage            = var.usage
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_snapshots.this.id
}

output "ids" {
  description = "returns a set of string"
  value       = data.alicloud_snapshots.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_snapshots.this.names
}

output "snapshots" {
  description = "returns a list of object"
  value       = data.alicloud_snapshots.this.snapshots
}

output "this" {
  value = alicloud_snapshots.this
}
```

[top](#index)