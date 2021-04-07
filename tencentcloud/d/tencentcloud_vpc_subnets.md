# tencentcloud_vpc_subnets

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
module "tencentcloud_vpc_subnets" {
  source = "./modules/tencentcloud/d/tencentcloud_vpc_subnets"

  # availability_zone - (optional) is a type of string
  availability_zone = null
  # cidr_block - (optional) is a type of string
  cidr_block = null
  # is_default - (optional) is a type of bool
  is_default = null
  # is_remote_vpc_snat - (optional) is a type of bool
  is_remote_vpc_snat = null
  # name - (optional) is a type of string
  name = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # subnet_id - (optional) is a type of string
  subnet_id = null
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
variable "availability_zone" {
  description = "(optional) - Zone of the subnet to be queried."
  type        = string
  default     = null
}

variable "cidr_block" {
  description = "(optional) - Filter subnet with this CIDR."
  type        = string
  default     = null
}

variable "is_default" {
  description = "(optional) - Filter default or no default subnets."
  type        = bool
  default     = null
}

variable "is_remote_vpc_snat" {
  description = "(optional) - Filter the VPC SNAT address pool subnet."
  type        = bool
  default     = null
}

variable "name" {
  description = "(optional) - Name of the subnet to be queried."
  type        = string
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "subnet_id" {
  description = "(optional) - ID of the subnet to be queried."
  type        = string
  default     = null
}

variable "tag_key" {
  description = "(optional) - Filter if subnet has this tag."
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - Tags of the subnet to be queried."
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
data "tencentcloud_vpc_subnets" "this" {
  # availability_zone - (optional) is a type of string
  availability_zone = var.availability_zone
  # cidr_block - (optional) is a type of string
  cidr_block = var.cidr_block
  # is_default - (optional) is a type of bool
  is_default = var.is_default
  # is_remote_vpc_snat - (optional) is a type of bool
  is_remote_vpc_snat = var.is_remote_vpc_snat
  # name - (optional) is a type of string
  name = var.name
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
  # subnet_id - (optional) is a type of string
  subnet_id = var.subnet_id
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
  value       = data.tencentcloud_vpc_subnets.this.id
}

output "instance_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_vpc_subnets.this.instance_list
}

output "this" {
  value = tencentcloud_vpc_subnets.this
}
```

[top](#index)