# tencentcloud_cfs_file_systems

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "tencentcloud_cfs_file_systems" {
  source = "./modules/tencentcloud/d/tencentcloud_cfs_file_systems"

  # availability_zone - (optional) is a type of string
  availability_zone = null
  # file_system_id - (optional) is a type of string
  file_system_id = null
  # name - (optional) is a type of string
  name = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # subnet_id - (optional) is a type of string
  subnet_id = null
  # vpc_id - (optional) is a type of string
  vpc_id = null
}
```

[top](#index)

### Variables

```terraform
variable "availability_zone" {
  description = "(optional) - The available zone that the file system locates at."
  type        = string
  default     = null
}

variable "file_system_id" {
  description = "(optional) - A specified file system ID used to query."
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - A file system name used to query."
  type        = string
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "subnet_id" {
  description = "(optional) - ID of a vpc subnet."
  type        = string
  default     = null
}

variable "vpc_id" {
  description = "(optional) - ID of the vpc to be queried."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_cfs_file_systems" "this" {
  availability_zone  = var.availability_zone
  file_system_id     = var.file_system_id
  name               = var.name
  result_output_file = var.result_output_file
  subnet_id          = var.subnet_id
  vpc_id             = var.vpc_id
}
```

[top](#index)

### Outputs

```terraform
output "file_system_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_cfs_file_systems.this.file_system_list
}

output "id" {
  description = "returns a string"
  value       = data.tencentcloud_cfs_file_systems.this.id
}

output "this" {
  value = tencentcloud_cfs_file_systems.this
}
```

[top](#index)