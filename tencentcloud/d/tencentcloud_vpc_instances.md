# tencentcloud_vpc_instances

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
module "tencentcloud_vpc_instances" {
  source = "./modules/tencentcloud/d/tencentcloud_vpc_instances"

  # cidr_block - (optional) is a type of string
  cidr_block = null
  # is_default - (optional) is a type of bool
  is_default = null
  # name - (optional) is a type of string
  name = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # tag_key - (optional) is a type of string
  tag_key = null
  # tags - (optional) is a type of map of string
  tags = {}
  # vpc_id - (optional) is a type of string
  vpc_id = null
}
```

[top](#index)

### Variables

```terraform
variable "cidr_block" {
  description = "(optional) - Filter VPC with this CIDR."
  type        = string
  default     = null
}

variable "is_default" {
  description = "(optional) - Filter default or no default VPC."
  type        = bool
  default     = null
}

variable "name" {
  description = "(optional) - Name of the VPC to be queried."
  type        = string
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "tag_key" {
  description = "(optional) - Filter if VPC has this tag."
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - Tags of the VPC to be queried."
  type        = map(string)
  default     = null
}

variable "vpc_id" {
  description = "(optional) - ID of the VPC to be queried."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_vpc_instances" "this" {
  # cidr_block - (optional) is a type of string
  cidr_block = var.cidr_block
  # is_default - (optional) is a type of bool
  is_default = var.is_default
  # name - (optional) is a type of string
  name = var.name
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
  # tag_key - (optional) is a type of string
  tag_key = var.tag_key
  # tags - (optional) is a type of map of string
  tags = var.tags
  # vpc_id - (optional) is a type of string
  vpc_id = var.vpc_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_vpc_instances.this.id
}

output "instance_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_vpc_instances.this.instance_list
}

output "this" {
  value = tencentcloud_vpc_instances.this
}
```

[top](#index)