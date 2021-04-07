# tencentcloud_dnats

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
module "tencentcloud_dnats" {
  source = "./modules/tencentcloud/d/tencentcloud_dnats"

  # description - (optional) is a type of string
  description = null
  # elastic_ip - (optional) is a type of string
  elastic_ip = null
  # elastic_port - (optional) is a type of string
  elastic_port = null
  # nat_id - (optional) is a type of string
  nat_id = null
  # private_ip - (optional) is a type of string
  private_ip = null
  # private_port - (optional) is a type of string
  private_port = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # vpc_id - (optional) is a type of string
  vpc_id = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Description of the NAT forward."
  type        = string
  default     = null
}

variable "elastic_ip" {
  description = "(optional) - Network address of the EIP."
  type        = string
  default     = null
}

variable "elastic_port" {
  description = "(optional) - Port of the EIP."
  type        = string
  default     = null
}

variable "nat_id" {
  description = "(optional) - ID of the NAT gateway."
  type        = string
  default     = null
}

variable "private_ip" {
  description = "(optional) - Network address of the backend service."
  type        = string
  default     = null
}

variable "private_port" {
  description = "(optional) - Port of intranet."
  type        = string
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "vpc_id" {
  description = "(optional) - ID of the VPC."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_dnats" "this" {
  # description - (optional) is a type of string
  description = var.description
  # elastic_ip - (optional) is a type of string
  elastic_ip = var.elastic_ip
  # elastic_port - (optional) is a type of string
  elastic_port = var.elastic_port
  # nat_id - (optional) is a type of string
  nat_id = var.nat_id
  # private_ip - (optional) is a type of string
  private_ip = var.private_ip
  # private_port - (optional) is a type of string
  private_port = var.private_port
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
  # vpc_id - (optional) is a type of string
  vpc_id = var.vpc_id
}
```

[top](#index)

### Outputs

```terraform
output "dnat_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_dnats.this.dnat_list
}

output "id" {
  description = "returns a string"
  value       = data.tencentcloud_dnats.this.id
}

output "this" {
  value = tencentcloud_dnats.this
}
```

[top](#index)