# tencentcloud_enis

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
module "tencentcloud_enis" {
  source = "./modules/tencentcloud/d/tencentcloud_enis"

  # description - (optional) is a type of string
  description = null
  # ids - (optional) is a type of set of string
  ids = []
  # instance_id - (optional) is a type of string
  instance_id = null
  # ipv4 - (optional) is a type of string
  ipv4 = null
  # name - (optional) is a type of string
  name = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # security_group - (optional) is a type of string
  security_group = null
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
variable "description" {
  description = "(optional) - Description of the ENI. Conflict with `ids`."
  type        = string
  default     = null
}

variable "ids" {
  description = "(optional) - ID of the ENIs to be queried. Conflict with `vpc_id`,`subnet_id`,`instance_id`,`security_group`,`name`,`ipv4` and `tags`."
  type        = set(string)
  default     = null
}

variable "instance_id" {
  description = "(optional) - ID of the instance which bind the ENI. Conflict with `ids`."
  type        = string
  default     = null
}

variable "ipv4" {
  description = "(optional) - Intranet IP of the ENI. Conflict with `ids`."
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - Name of the ENI to be queried. Conflict with `ids`."
  type        = string
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "security_group" {
  description = "(optional) - A set of security group IDs which bind the ENI. Conflict with `ids`."
  type        = string
  default     = null
}

variable "subnet_id" {
  description = "(optional) - ID of the subnet within this vpc to be queried. Conflict with `ids`."
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - Tags of the ENI. Conflict with `ids`."
  type        = map(string)
  default     = null
}

variable "vpc_id" {
  description = "(optional) - ID of the vpc to be queried. Conflict with `ids`."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_enis" "this" {
  # description - (optional) is a type of string
  description = var.description
  # ids - (optional) is a type of set of string
  ids = var.ids
  # instance_id - (optional) is a type of string
  instance_id = var.instance_id
  # ipv4 - (optional) is a type of string
  ipv4 = var.ipv4
  # name - (optional) is a type of string
  name = var.name
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
  # security_group - (optional) is a type of string
  security_group = var.security_group
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
output "enis" {
  description = "returns a list of object"
  value       = data.tencentcloud_enis.this.enis
}

output "id" {
  description = "returns a string"
  value       = data.tencentcloud_enis.this.id
}

output "this" {
  value = tencentcloud_enis.this
}
```

[top](#index)