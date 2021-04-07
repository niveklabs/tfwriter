# tencentcloud_vpc_acls

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
module "tencentcloud_vpc_acls" {
  source = "./modules/tencentcloud/d/tencentcloud_vpc_acls"

  # name - (optional) is a type of string
  name = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # vpc_id - (optional) is a type of string
  vpc_id = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional) - Name of the network ACL."
  type        = string
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "vpc_id" {
  description = "(optional) - ID of the VPC instance."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_vpc_acls" "this" {
  # name - (optional) is a type of string
  name = var.name
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
  # vpc_id - (optional) is a type of string
  vpc_id = var.vpc_id
}
```

[top](#index)

### Outputs

```terraform
output "acl_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_vpc_acls.this.acl_list
}

output "id" {
  description = "returns a string"
  value       = data.tencentcloud_vpc_acls.this.id
}

output "this" {
  value = tencentcloud_vpc_acls.this
}
```

[top](#index)