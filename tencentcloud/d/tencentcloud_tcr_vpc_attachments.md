# tencentcloud_tcr_vpc_attachments

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
module "tencentcloud_tcr_vpc_attachments" {
  source = "./modules/tencentcloud/d/tencentcloud_tcr_vpc_attachments"

  # instance_id - (required) is a type of string
  instance_id = null
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
variable "instance_id" {
  description = "(required) - ID of the instance to query."
  type        = string
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "subnet_id" {
  description = "(optional) - ID of subnet to query."
  type        = string
  default     = null
}

variable "vpc_id" {
  description = "(optional) - ID of VPC to query."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_tcr_vpc_attachments" "this" {
  instance_id        = var.instance_id
  result_output_file = var.result_output_file
  subnet_id          = var.subnet_id
  vpc_id             = var.vpc_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_tcr_vpc_attachments.this.id
}

output "vpc_attachment_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_tcr_vpc_attachments.this.vpc_attachment_list
}

output "this" {
  value = tencentcloud_tcr_vpc_attachments.this
}
```

[top](#index)