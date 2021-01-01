# aws_ami
[back](../aws.md)
### Index
- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)
### Terraform
```hcl
terraform {
  required_providers {
    aws = ">= 3.22.0"
  }
}
```
[top](#index)
### Example Usage
```hcl
module "aws_ami" {
  source = "./modules/aws/d/aws_ami"

  # executable_users - (optional) is a type of list of string
  executable_users = []
  # most_recent - (optional) is a type of bool
  most_recent = null
  # name_regex - (optional) is a type of string
  name_regex = null
  # owners - (required) is a type of list of string
  owners = []
  # tags - (optional) is a type of map of string
  tags = {}

  filter = [{
    name   = null
    values = []
  }]
}
```
[top](#index)
### Variables
```hcl
variable "executable_users" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "most_recent" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "owners" {
  description = "(required)"
  type        = list(string)
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "filter" {
  description = "nested mode: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name   = string
      values = list(string)
    }
  ))
  default = []
}
```
[top](#index)

### Datasource
```hcl
data "aws_ami" "this" {
  executable_users = var.executable_users
  most_recent      = var.most_recent
  name_regex       = var.name_regex
  owners           = var.owners
  tags             = var.tags

  dynamic "filter" {
    for_each = var.filter
    content {
      name   = filter.value["name"]
      values = filter.value["values"]
    }
  }

}
```
[top](#index)
### Outputs
```hcl
output "architecture" {
  description = "returns a string"
  value       = data.aws_ami.this.architecture
}

output "arn" {
  description = "returns a string"
  value       = data.aws_ami.this.arn
}

output "block_device_mappings" {
  description = "returns a set of object"
  value       = data.aws_ami.this.block_device_mappings
}

output "creation_date" {
  description = "returns a string"
  value       = data.aws_ami.this.creation_date
}

output "description" {
  description = "returns a string"
  value       = data.aws_ami.this.description
}

output "hypervisor" {
  description = "returns a string"
  value       = data.aws_ami.this.hypervisor
}

output "id" {
  description = "returns a string"
  value       = data.aws_ami.this.id
}

output "image_id" {
  description = "returns a string"
  value       = data.aws_ami.this.image_id
}

output "image_location" {
  description = "returns a string"
  value       = data.aws_ami.this.image_location
}

output "image_owner_alias" {
  description = "returns a string"
  value       = data.aws_ami.this.image_owner_alias
}

output "image_type" {
  description = "returns a string"
  value       = data.aws_ami.this.image_type
}

output "kernel_id" {
  description = "returns a string"
  value       = data.aws_ami.this.kernel_id
}

output "name" {
  description = "returns a string"
  value       = data.aws_ami.this.name
}

output "owner_id" {
  description = "returns a string"
  value       = data.aws_ami.this.owner_id
}

output "platform" {
  description = "returns a string"
  value       = data.aws_ami.this.platform
}

output "product_codes" {
  description = "returns a set of object"
  value       = data.aws_ami.this.product_codes
}

output "public" {
  description = "returns a bool"
  value       = data.aws_ami.this.public
}

output "ramdisk_id" {
  description = "returns a string"
  value       = data.aws_ami.this.ramdisk_id
}

output "root_device_name" {
  description = "returns a string"
  value       = data.aws_ami.this.root_device_name
}

output "root_device_type" {
  description = "returns a string"
  value       = data.aws_ami.this.root_device_type
}

output "root_snapshot_id" {
  description = "returns a string"
  value       = data.aws_ami.this.root_snapshot_id
}

output "sriov_net_support" {
  description = "returns a string"
  value       = data.aws_ami.this.sriov_net_support
}

output "state" {
  description = "returns a string"
  value       = data.aws_ami.this.state
}

output "state_reason" {
  description = "returns a map of string"
  value       = data.aws_ami.this.state_reason
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_ami.this.tags
}

output "virtualization_type" {
  description = "returns a string"
  value       = data.aws_ami.this.virtualization_type
}

output "this" {
  value = aws_ami.this
}
```
[top](#index)
