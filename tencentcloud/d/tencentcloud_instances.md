# tencentcloud_instances

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
module "tencentcloud_instances" {
  source = "./modules/tencentcloud/d/tencentcloud_instances"

  # availability_zone - (optional) is a type of string
  availability_zone = null
  # instance_id - (optional) is a type of string
  instance_id = null
  # instance_name - (optional) is a type of string
  instance_name = null
  # project_id - (optional) is a type of number
  project_id = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # subnet_id - (optional) is a type of string
  subnet_id = null
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
  description = "(optional) - The available zone that the CVM instance locates at."
  type        = string
  default     = null
}

variable "instance_id" {
  description = "(optional) - ID of the instances to be queried."
  type        = string
  default     = null
}

variable "instance_name" {
  description = "(optional) - Name of the instances to be queried."
  type        = string
  default     = null
}

variable "project_id" {
  description = "(optional) - The project CVM belongs to."
  type        = number
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "subnet_id" {
  description = "(optional) - ID of a vpc subnetwork."
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - Tags of the instance."
  type        = map(string)
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
data "tencentcloud_instances" "this" {
  # availability_zone - (optional) is a type of string
  availability_zone = var.availability_zone
  # instance_id - (optional) is a type of string
  instance_id = var.instance_id
  # instance_name - (optional) is a type of string
  instance_name = var.instance_name
  # project_id - (optional) is a type of number
  project_id = var.project_id
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
  # subnet_id - (optional) is a type of string
  subnet_id = var.subnet_id
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
  value       = data.tencentcloud_instances.this.id
}

output "instance_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_instances.this.instance_list
}

output "this" {
  value = tencentcloud_instances.this
}
```

[top](#index)