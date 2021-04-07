# tencentcloud_cfs_file_system

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
module "tencentcloud_cfs_file_system" {
  source = "./modules/tencentcloud/r/tencentcloud_cfs_file_system"

  # access_group_id - (required) is a type of string
  access_group_id = null
  # availability_zone - (required) is a type of string
  availability_zone = null
  # mount_ip - (optional) is a type of string
  mount_ip = null
  # name - (optional) is a type of string
  name = null
  # protocol - (optional) is a type of string
  protocol = null
  # storage_type - (optional) is a type of string
  storage_type = null
  # subnet_id - (required) is a type of string
  subnet_id = null
  # tags - (optional) is a type of map of string
  tags = {}
  # vpc_id - (required) is a type of string
  vpc_id = null
}
```

[top](#index)

### Variables

```terraform
variable "access_group_id" {
  description = "(required) - ID of a access group."
  type        = string
}

variable "availability_zone" {
  description = "(required) - The available zone that the file system locates at."
  type        = string
}

variable "mount_ip" {
  description = "(optional) - IP of mount point."
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - Name of a file system."
  type        = string
  default     = null
}

variable "protocol" {
  description = "(optional) - File service protocol. Valid values are `NFS` and `CIFS`. and the default is `NFS`."
  type        = string
  default     = null
}

variable "storage_type" {
  description = "(optional) - File service StorageType. Valid values are `SD` and `HP`. and the default is `SD`."
  type        = string
  default     = null
}

variable "subnet_id" {
  description = "(required) - ID of a subnet."
  type        = string
}

variable "tags" {
  description = "(optional) - Instance tags."
  type        = map(string)
  default     = null
}

variable "vpc_id" {
  description = "(required) - ID of a VPC network."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_cfs_file_system" "this" {
  access_group_id   = var.access_group_id
  availability_zone = var.availability_zone
  mount_ip          = var.mount_ip
  name              = var.name
  protocol          = var.protocol
  storage_type      = var.storage_type
  subnet_id         = var.subnet_id
  tags              = var.tags
  vpc_id            = var.vpc_id
}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = tencentcloud_cfs_file_system.this.create_time
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_cfs_file_system.this.id
}

output "mount_ip" {
  description = "returns a string"
  value       = tencentcloud_cfs_file_system.this.mount_ip
}

output "name" {
  description = "returns a string"
  value       = tencentcloud_cfs_file_system.this.name
}

output "this" {
  value = tencentcloud_cfs_file_system.this
}
```

[top](#index)